---
title: 导出每个设备的软件漏洞评估
description: API 响应针对每个设备，并且包含安装在公开设备上易受攻击的软件，以及这些软件产品中的任何已知漏洞。 此表还包括操作系统信息、CVE ID 和漏洞严重性信息。
keywords: api， api， 导出评估， 按设备评估， 漏洞评估报告， 设备漏洞评估， 设备漏洞报告， 安全配置评估， 安全配置报告， 软件漏洞评估， 软件漏洞报告， 计算机漏洞报告，
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6243da415c5cc509be33eabffd12516367164bff
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022866"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="e5c44-105">导出每个设备的软件漏洞评估</span><span class="sxs-lookup"><span data-stu-id="e5c44-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e5c44-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e5c44-106">**Applies to:**</span></span>

- [<span data-ttu-id="e5c44-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e5c44-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e5c44-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5c44-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e5c44-109">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e5c44-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e5c44-110">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e5c44-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="e5c44-111">基于每个设备返回所有已知软件漏洞及其所有设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5c44-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="e5c44-112">不同的 API 调用用于获取不同类型的数据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="e5c44-113">由于数据量可能非常大，因此有两种方法可以检索数据：</span><span class="sxs-lookup"><span data-stu-id="e5c44-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="e5c44-114">[导出软件漏洞评估 **JSON 响应**](#1-export-software-vulnerabilities-assessment-json-response)  API 将提取组织的所有数据作为 Json 响应。</span><span class="sxs-lookup"><span data-stu-id="e5c44-114">[Export software vulnerabilities assessment **JSON response**](#1-export-software-vulnerabilities-assessment-json-response)  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="e5c44-115">此方法最适合使用少于 _100 K_ 设备的小组织。</span><span class="sxs-lookup"><span data-stu-id="e5c44-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="e5c44-116">响应会分页，因此您可以使用响应中的 \@ odata.nextLink 字段获取下一个结果。</span><span class="sxs-lookup"><span data-stu-id="e5c44-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="e5c44-117">[通过文件导出软件 **漏洞评估**](#2-export-software-vulnerabilities-assessment-via-files) 此 API 解决方案允许更快、更可靠地提取大量数据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-117">[Export software vulnerabilities assessment **via files**](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="e5c44-118">对于拥有 100 K 多台设备的大型组织，建议使用 Via-files。</span><span class="sxs-lookup"><span data-stu-id="e5c44-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="e5c44-119">此 API 将组织的所有数据提取为下载文件。</span><span class="sxs-lookup"><span data-stu-id="e5c44-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="e5c44-120">该响应包含从网站下载所有数据的Azure 存储空间。</span><span class="sxs-lookup"><span data-stu-id="e5c44-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="e5c44-121">通过此 API，可以从以下Azure 存储空间下载所有数据：</span><span class="sxs-lookup"><span data-stu-id="e5c44-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="e5c44-122">调用 API 获取包含所有组织数据的下载 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="e5c44-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="e5c44-123">使用下载 URL 下载所有文件并处理您喜欢的数据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="e5c44-124">[Delta 导出软件漏洞评估 **JSON 响应**](#3-delta-export-software-vulnerabilities-assessment-json-response)  返回一个表，其中每个唯一组合都有一个条目：DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 和 EventTimestamp。</span><span class="sxs-lookup"><span data-stu-id="e5c44-124">[Delta export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="e5c44-125">API 拉取你组织的数据作为 Json 响应。</span><span class="sxs-lookup"><span data-stu-id="e5c44-125">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="e5c44-126">响应将分页，因此您可以使用响应中的 @odata.nextLink 字段获取下一个结果。</span><span class="sxs-lookup"><span data-stu-id="e5c44-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="e5c44-127">与完整的"软件漏洞评估 (JSON 响应) "不同（用于按设备获取组织的软件漏洞评估的完整快照）不同，增量导出 OData API 调用仅用于获取所选日期和当前日期之间发生的更改 ("delta"API 调用) 。</span><span class="sxs-lookup"><span data-stu-id="e5c44-127">Unlike the full "software vulnerabilities assessment (JSON response)" - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="e5c44-128">您不会每次获取包含大量数据的完全导出，而只会获取有关新的、已修复和更新的漏洞的特定信息。</span><span class="sxs-lookup"><span data-stu-id="e5c44-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="e5c44-129">Delta 导出 JSON 响应 API 调用还可用于计算不同的 KPI，例如"修复了多少漏洞？"</span><span class="sxs-lookup"><span data-stu-id="e5c44-129">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="e5c44-130">或"向我的组织添加了多少个新漏洞？"</span><span class="sxs-lookup"><span data-stu-id="e5c44-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="e5c44-131">由于针对软件漏洞的 Delta 导出 JSON 响应 API 调用仅返回目标日期范围的数据，因此不被视为完全 _导出_。</span><span class="sxs-lookup"><span data-stu-id="e5c44-131">Because the Delta export JSON response API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="e5c44-132">使用 _OData_ 或 (文件收集的数据) 当前状态的当前快照，不包含历史数据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-132">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="e5c44-133">为了收集历史数据，客户必须将数据保存在自己的数据存储中。</span><span class="sxs-lookup"><span data-stu-id="e5c44-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="e5c44-134">除非另有说明，否则列出的所有导出评估方法都是 \*\*\*\* 完全导出 (\*\*\*\* 也称作按设备 **_) 。_**</span><span class="sxs-lookup"><span data-stu-id="e5c44-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="e5c44-135">1. 导出 JSON 响应 (软件漏洞) </span><span class="sxs-lookup"><span data-stu-id="e5c44-135">1. Export software vulnerabilities assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="e5c44-136">1.1 API 方法说明</span><span class="sxs-lookup"><span data-stu-id="e5c44-136">1.1 API method description</span></span>

<span data-ttu-id="e5c44-137">此 API 响应包含每个设备已安装软件的所有数据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="e5c44-138">返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 每个唯一组合的条目的表。</span><span class="sxs-lookup"><span data-stu-id="e5c44-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="e5c44-139">1.1.1 限制</span><span class="sxs-lookup"><span data-stu-id="e5c44-139">1.1.1 Limitations</span></span>

- <span data-ttu-id="e5c44-140">最大页面大小为 200，000。</span><span class="sxs-lookup"><span data-stu-id="e5c44-140">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="e5c44-141">此 API 的速率限制是每分钟 30 个调用和每小时 1000 个调用。</span><span class="sxs-lookup"><span data-stu-id="e5c44-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="e5c44-142">1.2 权限</span><span class="sxs-lookup"><span data-stu-id="e5c44-142">1.2 Permissions</span></span>

<span data-ttu-id="e5c44-143">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="e5c44-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e5c44-144">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e5c44-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="e5c44-145">权限类型</span><span class="sxs-lookup"><span data-stu-id="e5c44-145">Permission type</span></span> | <span data-ttu-id="e5c44-146">权限</span><span class="sxs-lookup"><span data-stu-id="e5c44-146">Permission</span></span> | <span data-ttu-id="e5c44-147">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="e5c44-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="e5c44-148">应用程序</span><span class="sxs-lookup"><span data-stu-id="e5c44-148">Application</span></span> | <span data-ttu-id="e5c44-149">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="e5c44-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="e5c44-150">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="e5c44-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="e5c44-151">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="e5c44-151">Delegated (work or school account)</span></span> | <span data-ttu-id="e5c44-152">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="e5c44-152">Vulnerability.Read</span></span> | <span data-ttu-id="e5c44-153">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="e5c44-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="e5c44-154">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="e5c44-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="e5c44-155">1.4 参数</span><span class="sxs-lookup"><span data-stu-id="e5c44-155">1.4 Parameters</span></span>

- <span data-ttu-id="e5c44-156">pageSize (默认值 = 50，000) – 响应中的结果数</span><span class="sxs-lookup"><span data-stu-id="e5c44-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="e5c44-157">$top – 要返回 (的结果数不会返回 @odata.nextLink，因此不会拉取所有) </span><span class="sxs-lookup"><span data-stu-id="e5c44-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="e5c44-158">1.5 属性</span><span class="sxs-lookup"><span data-stu-id="e5c44-158">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="e5c44-159">每条记录大约包含 1 KB 的数据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-159">Each record is approximately 1 KB of data.</span></span> <span data-ttu-id="e5c44-160">在选择正确的 pageSize 参数时，您应当考虑到这一点。</span><span class="sxs-lookup"><span data-stu-id="e5c44-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="e5c44-161">响应中可能会返回其他一些列。</span><span class="sxs-lookup"><span data-stu-id="e5c44-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="e5c44-162">这些列是临时的，可能会被删除，请仅使用记录列。</span><span class="sxs-lookup"><span data-stu-id="e5c44-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="e5c44-163">下表中定义的属性按字母顺序按属性 ID 列出。</span><span class="sxs-lookup"><span data-stu-id="e5c44-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="e5c44-164">运行此 API 时，生成的输出不必按此表中列出的相同顺序返回。</span><span class="sxs-lookup"><span data-stu-id="e5c44-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>

<br/>

<span data-ttu-id="e5c44-165">属性 (ID) </span><span class="sxs-lookup"><span data-stu-id="e5c44-165">Property (ID)</span></span> | <span data-ttu-id="e5c44-166">数据类型</span><span class="sxs-lookup"><span data-stu-id="e5c44-166">Data type</span></span> | <span data-ttu-id="e5c44-167">说明</span><span class="sxs-lookup"><span data-stu-id="e5c44-167">Description</span></span> | <span data-ttu-id="e5c44-168">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="e5c44-169">CveId</span><span class="sxs-lookup"><span data-stu-id="e5c44-169">CveId</span></span> | <span data-ttu-id="e5c44-170">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-170">string</span></span> | <span data-ttu-id="e5c44-171">分配给 CVE 安全机制中常见漏洞和 (漏洞) 标识符。</span><span class="sxs-lookup"><span data-stu-id="e5c44-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="e5c44-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="e5c44-172">CVE-2020-15992</span></span>
<span data-ttu-id="e5c44-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="e5c44-173">CvssScore</span></span> | <span data-ttu-id="e5c44-174">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-174">string</span></span> | <span data-ttu-id="e5c44-175">CVE 的 CVSS 分数。</span><span class="sxs-lookup"><span data-stu-id="e5c44-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="e5c44-176">6.2</span><span class="sxs-lookup"><span data-stu-id="e5c44-176">6.2</span></span>
<span data-ttu-id="e5c44-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="e5c44-177">DeviceId</span></span> | <span data-ttu-id="e5c44-178">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-178">string</span></span> | <span data-ttu-id="e5c44-179">服务中设备的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e5c44-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="e5c44-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="e5c44-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="e5c44-181">DeviceName</span><span class="sxs-lookup"><span data-stu-id="e5c44-181">DeviceName</span></span> | <span data-ttu-id="e5c44-182">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-182">string</span></span> | <span data-ttu-id="e5c44-183">设备的完全限定 (FQDN) FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5c44-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="e5c44-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e5c44-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="e5c44-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="e5c44-185">DiskPaths</span></span>  | <span data-ttu-id="e5c44-186">数组 \[ 字符串\]</span><span class="sxs-lookup"><span data-stu-id="e5c44-186">Array\[string\]</span></span> | <span data-ttu-id="e5c44-187">表明产品已安装在设备的磁盘证据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="e5c44-188">[ "C：\Program Files (x86) \Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="e5c44-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="e5c44-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="e5c44-189">ExploitabilityLevel</span></span> | <span data-ttu-id="e5c44-190">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-190">string</span></span> | <span data-ttu-id="e5c44-191">此漏洞的利用级别 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) </span><span class="sxs-lookup"><span data-stu-id="e5c44-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="e5c44-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="e5c44-192">ExploitIsInKit</span></span>
<span data-ttu-id="e5c44-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="e5c44-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="e5c44-194">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-194">string</span></span> | <span data-ttu-id="e5c44-195">首次在设备上看到此产品的 CVE 时。</span><span class="sxs-lookup"><span data-stu-id="e5c44-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="e5c44-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="e5c44-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="e5c44-197">Id</span><span class="sxs-lookup"><span data-stu-id="e5c44-197">Id</span></span> | <span data-ttu-id="e5c44-198">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-198">string</span></span> | <span data-ttu-id="e5c44-199">记录的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e5c44-199">Unique identifier for the record.</span></span> | <span data-ttu-id="e5c44-200">123ABG55_573AG&mnp！</span><span class="sxs-lookup"><span data-stu-id="e5c44-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="e5c44-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="e5c44-201">LastSeenTimestamp</span></span> | <span data-ttu-id="e5c44-202">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-202">string</span></span> | <span data-ttu-id="e5c44-203">上次在设备上看到 CVE 的时间。</span><span class="sxs-lookup"><span data-stu-id="e5c44-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="e5c44-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="e5c44-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="e5c44-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="e5c44-205">OSPlatform</span></span> | <span data-ttu-id="e5c44-206">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-206">string</span></span> | <span data-ttu-id="e5c44-207">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="e5c44-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e5c44-208">此属性指示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="e5c44-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="e5c44-209">有关详细信息，请参阅 tvm 支持的操作系统和平台。</span><span class="sxs-lookup"><span data-stu-id="e5c44-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="e5c44-210">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e5c44-210">Windows10</span></span>
<span data-ttu-id="e5c44-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="e5c44-211">RbacGroupName</span></span>  | <span data-ttu-id="e5c44-212">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-212">string</span></span> | <span data-ttu-id="e5c44-213">基于角色的访问控制 (RBAC) 组。</span><span class="sxs-lookup"><span data-stu-id="e5c44-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="e5c44-214">如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。</span><span class="sxs-lookup"><span data-stu-id="e5c44-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="e5c44-215">如果组织不包含任何 RBAC 组，则值为"None"。</span><span class="sxs-lookup"><span data-stu-id="e5c44-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="e5c44-216">服务器</span><span class="sxs-lookup"><span data-stu-id="e5c44-216">Servers</span></span>
<span data-ttu-id="e5c44-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="e5c44-217">RecommendationReference</span></span> | <span data-ttu-id="e5c44-218">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-218">string</span></span> | <span data-ttu-id="e5c44-219">对此软件相关建议 ID 的引用。</span><span class="sxs-lookup"><span data-stu-id="e5c44-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="e5c44-220">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="e5c44-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="e5c44-221">RecommendedSecurityUpdate (可选) </span><span class="sxs-lookup"><span data-stu-id="e5c44-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="e5c44-222">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-222">string</span></span> | <span data-ttu-id="e5c44-223">软件供应商提供的用于解决漏洞的安全更新的名称或说明。</span><span class="sxs-lookup"><span data-stu-id="e5c44-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="e5c44-224">2020 年 4 月安全更新</span><span class="sxs-lookup"><span data-stu-id="e5c44-224">April 2020 Security Updates</span></span>
<span data-ttu-id="e5c44-225">RecommendedSecurityUpdateId (可选) </span><span class="sxs-lookup"><span data-stu-id="e5c44-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="e5c44-226">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-226">string</span></span> | <span data-ttu-id="e5c44-227">相应指南或知识库的适用安全更新或标识符的标识符 (KB) 文章</span><span class="sxs-lookup"><span data-stu-id="e5c44-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="e5c44-228">4550961</span><span class="sxs-lookup"><span data-stu-id="e5c44-228">4550961</span></span>
<span data-ttu-id="e5c44-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="e5c44-229">RegistryPaths</span></span>  | <span data-ttu-id="e5c44-230">数组 \[ 字符串\]</span><span class="sxs-lookup"><span data-stu-id="e5c44-230">Array\[string\]</span></span> | <span data-ttu-id="e5c44-231">注册表证据，表明产品已安装在设备中。</span><span class="sxs-lookup"><span data-stu-id="e5c44-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="e5c44-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="e5c44-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="e5c44-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="e5c44-233">SoftwareName</span></span> | <span data-ttu-id="e5c44-234">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-234">string</span></span> | <span data-ttu-id="e5c44-235">软件产品的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c44-235">Name of the software product.</span></span> | <span data-ttu-id="e5c44-236">chrome</span><span class="sxs-lookup"><span data-stu-id="e5c44-236">chrome</span></span>
<span data-ttu-id="e5c44-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="e5c44-237">SoftwareVendor</span></span> | <span data-ttu-id="e5c44-238">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-238">string</span></span> | <span data-ttu-id="e5c44-239">软件供应商的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c44-239">Name of the software vendor.</span></span> | <span data-ttu-id="e5c44-240">google</span><span class="sxs-lookup"><span data-stu-id="e5c44-240">google</span></span>
<span data-ttu-id="e5c44-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="e5c44-241">SoftwareVersion</span></span> | <span data-ttu-id="e5c44-242">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-242">string</span></span> | <span data-ttu-id="e5c44-243">软件产品的版本号。</span><span class="sxs-lookup"><span data-stu-id="e5c44-243">Version number of the software product.</span></span> | <span data-ttu-id="e5c44-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="e5c44-244">81.0.4044.138</span></span>
<span data-ttu-id="e5c44-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="e5c44-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="e5c44-246">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-246">string</span></span> | <span data-ttu-id="e5c44-247">根据 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="e5c44-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="e5c44-248">中</span><span class="sxs-lookup"><span data-stu-id="e5c44-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="e5c44-249">1.6 示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="e5c44-250">1.6.1 请求示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="e5c44-251">1.6.2 响应示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-251">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="e5c44-252">2. 通过文件 (导出软件漏洞) </span><span class="sxs-lookup"><span data-stu-id="e5c44-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="e5c44-253">2.1 API 方法说明</span><span class="sxs-lookup"><span data-stu-id="e5c44-253">2.1 API method description</span></span>

<span data-ttu-id="e5c44-254">此 API 响应包含每个设备已安装软件的所有数据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="e5c44-255">返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID 每个唯一组合的条目的表。</span><span class="sxs-lookup"><span data-stu-id="e5c44-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="e5c44-256">2.1.2 限制</span><span class="sxs-lookup"><span data-stu-id="e5c44-256">2.1.2 Limitations</span></span>

<span data-ttu-id="e5c44-257">此 API 的速率限制是每分钟 5 个调用和每小时 20 个调用。</span><span class="sxs-lookup"><span data-stu-id="e5c44-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="e5c44-258">2.2 权限</span><span class="sxs-lookup"><span data-stu-id="e5c44-258">2.2 Permissions</span></span>

<span data-ttu-id="e5c44-259">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="e5c44-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e5c44-260">若要了解详细信息，包括如何选择权限，请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c44-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="e5c44-261">权限类型</span><span class="sxs-lookup"><span data-stu-id="e5c44-261">Permission type</span></span> | <span data-ttu-id="e5c44-262">权限</span><span class="sxs-lookup"><span data-stu-id="e5c44-262">Permission</span></span> | <span data-ttu-id="e5c44-263">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="e5c44-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="e5c44-264">应用程序</span><span class="sxs-lookup"><span data-stu-id="e5c44-264">Application</span></span> | <span data-ttu-id="e5c44-265">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="e5c44-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="e5c44-266">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="e5c44-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="e5c44-267">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="e5c44-267">Delegated (work or school account)</span></span> | <span data-ttu-id="e5c44-268">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="e5c44-268">Vulnerability.Read</span></span> | <span data-ttu-id="e5c44-269">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="e5c44-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="e5c44-270">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="e5c44-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="e5c44-271">2.4 参数</span><span class="sxs-lookup"><span data-stu-id="e5c44-271">2.4 Parameters</span></span>

- <span data-ttu-id="e5c44-272">sasValidHours – 下载 URL 在最长 24 小时 (的有效小时数) </span><span class="sxs-lookup"><span data-stu-id="e5c44-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="e5c44-273">2.5 属性</span><span class="sxs-lookup"><span data-stu-id="e5c44-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="e5c44-274">文件是 gzip 压缩文件& Json 格式。</span><span class="sxs-lookup"><span data-stu-id="e5c44-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="e5c44-275">下载 URL 的有效期仅为 3 小时;否则，可以使用 参数。</span><span class="sxs-lookup"><span data-stu-id="e5c44-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="e5c44-276">为了最大限度提高数据的下载速度，你可以确保从数据所在的同一 Azure 区域进行下载。</span><span class="sxs-lookup"><span data-stu-id="e5c44-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="e5c44-277">每条记录大约包含 1KB 的数据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="e5c44-278">在选择正确的 pageSize 参数时，您应当考虑到这一点。</span><span class="sxs-lookup"><span data-stu-id="e5c44-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="e5c44-279">响应中可能会返回其他一些列。</span><span class="sxs-lookup"><span data-stu-id="e5c44-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="e5c44-280">这些列是临时的，可能会被删除，请仅使用记录列。</span><span class="sxs-lookup"><span data-stu-id="e5c44-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="e5c44-281">属性 (ID) </span><span class="sxs-lookup"><span data-stu-id="e5c44-281">Property (ID)</span></span> | <span data-ttu-id="e5c44-282">数据类型</span><span class="sxs-lookup"><span data-stu-id="e5c44-282">Data type</span></span> | <span data-ttu-id="e5c44-283">说明</span><span class="sxs-lookup"><span data-stu-id="e5c44-283">Description</span></span> | <span data-ttu-id="e5c44-284">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="e5c44-285">导出文件</span><span class="sxs-lookup"><span data-stu-id="e5c44-285">Export files</span></span> | <span data-ttu-id="e5c44-286">数组 \[ 字符串\]</span><span class="sxs-lookup"><span data-stu-id="e5c44-286">array\[string\]</span></span>  | <span data-ttu-id="e5c44-287">保存组织当前快照的文件的下载 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="e5c44-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="e5c44-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="e5c44-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="e5c44-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="e5c44-289">GeneratedTime</span></span> | <span data-ttu-id="e5c44-290">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-290">string</span></span> | <span data-ttu-id="e5c44-291">导出的生成时间。</span><span class="sxs-lookup"><span data-stu-id="e5c44-291">The time that the export was generated.</span></span> | <span data-ttu-id="e5c44-292">2021-05-20T08：00：00Z</span><span class="sxs-lookup"><span data-stu-id="e5c44-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="e5c44-293">2.6 示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="e5c44-294">2.6.1 请求示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="e5c44-295">2.6.2 响应示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-295">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="e5c44-296">3. Delta 导出软件漏洞评估 (JSON 响应) </span><span class="sxs-lookup"><span data-stu-id="e5c44-296">3. Delta export software vulnerabilities assessment (JSON response)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="e5c44-297">3.1 API 方法说明</span><span class="sxs-lookup"><span data-stu-id="e5c44-297">3.1 API method description</span></span>

<span data-ttu-id="e5c44-298">返回一个包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId 每个唯一组合的条目的表。</span><span class="sxs-lookup"><span data-stu-id="e5c44-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="e5c44-299">API 拉取你组织的数据作为 Json 响应。</span><span class="sxs-lookup"><span data-stu-id="e5c44-299">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="e5c44-300">响应将分页，因此您可以使用响应中的 @odata.nextLink 字段获取下一个结果。</span><span class="sxs-lookup"><span data-stu-id="e5c44-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="e5c44-301">与完整的软件漏洞评估 (JSON 响应) （用于按设备获取组织的软件漏洞评估的完整快照）不同，增量导出 JSON 响应 API 调用仅用于获取所选日期与当前日期之间发生的更改 ("delta"API 调用) 。</span><span class="sxs-lookup"><span data-stu-id="e5c44-301">Unlike the full software vulnerabilities assessment (JSON response)—which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device—the delta export JSON response API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="e5c44-302">您不会每次获取包含大量数据的完全导出，而只会获取有关新的、已修复和更新的漏洞的特定信息。</span><span class="sxs-lookup"><span data-stu-id="e5c44-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="e5c44-303">Delta 导出 JSON 响应 API 调用还可用于计算不同的 KPI，例如"修复了多少漏洞？"</span><span class="sxs-lookup"><span data-stu-id="e5c44-303">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="e5c44-304">或"向我的组织添加了多少个新漏洞？"</span><span class="sxs-lookup"><span data-stu-id="e5c44-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="e5c44-305">强烈建议你至少每周使用一次通过设备 API 调用评估的完整导出软件漏洞，此额外的导出软件漏洞会通过设备 (delta) API 调用一周中的所有其他日期进行更改。</span><span class="sxs-lookup"><span data-stu-id="e5c44-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="e5c44-306">与其他评估 JSON 响应 API 不同，"增量导出"不是完全导出。</span><span class="sxs-lookup"><span data-stu-id="e5c44-306">Unlike the other Assessments JSON response APIs, the “delta export” is not a full export.</span></span> <span data-ttu-id="e5c44-307">增量导出仅包括所选日期与当前日期之间发生的更改 ("delta"API 调用) 。</span><span class="sxs-lookup"><span data-stu-id="e5c44-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="311-limitations"></a><span data-ttu-id="e5c44-308">3.1.1 限制</span><span class="sxs-lookup"><span data-stu-id="e5c44-308">3.1.1 Limitations</span></span>

- <span data-ttu-id="e5c44-309">最大页面大小为 200，000。</span><span class="sxs-lookup"><span data-stu-id="e5c44-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="e5c44-310">sinceTime 参数最长为 14 天。</span><span class="sxs-lookup"><span data-stu-id="e5c44-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="e5c44-311">此 API 的速率限制是每分钟 30 个调用和每小时 1000 个调用。</span><span class="sxs-lookup"><span data-stu-id="e5c44-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="e5c44-312">3.2 权限</span><span class="sxs-lookup"><span data-stu-id="e5c44-312">3.2 Permissions</span></span>

<span data-ttu-id="e5c44-313">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="e5c44-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e5c44-314">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e5c44-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="e5c44-315">权限类型</span><span class="sxs-lookup"><span data-stu-id="e5c44-315">Permission type</span></span> | <span data-ttu-id="e5c44-316">权限</span><span class="sxs-lookup"><span data-stu-id="e5c44-316">Permission</span></span> | <span data-ttu-id="e5c44-317">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="e5c44-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="e5c44-318">应用程序</span><span class="sxs-lookup"><span data-stu-id="e5c44-318">Application</span></span> | <span data-ttu-id="e5c44-319">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="e5c44-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="e5c44-320">"读取威胁和漏洞管理漏洞信息"</span><span class="sxs-lookup"><span data-stu-id="e5c44-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="e5c44-321">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="e5c44-321">Delegated (work or school account)</span></span> | <span data-ttu-id="e5c44-322">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="e5c44-322">Vulnerability.Read</span></span> | <span data-ttu-id="e5c44-323">"读取威胁和漏洞管理漏洞信息"</span><span class="sxs-lookup"><span data-stu-id="e5c44-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="e5c44-324">3.3 URL</span><span class="sxs-lookup"><span data-stu-id="e5c44-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="e5c44-325">3.4 参数</span><span class="sxs-lookup"><span data-stu-id="e5c44-325">3.4 Parameters</span></span>

- <span data-ttu-id="e5c44-326">sinceTime (必) – 所选时间和今天之间的数据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="e5c44-327">pageSize (默认值 = 50，000) – 响应中的结果数</span><span class="sxs-lookup"><span data-stu-id="e5c44-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="e5c44-328">$top – 要返回 (的结果数不会返回 @odata.nextLink，因此不会拉取所有) </span><span class="sxs-lookup"><span data-stu-id="e5c44-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="e5c44-329">3.5 属性</span><span class="sxs-lookup"><span data-stu-id="e5c44-329">3.5 Properties</span></span>

<span data-ttu-id="e5c44-330">每个返回的记录都包含设备 OData API 评估的完整导出软件漏洞的所有数据，以及两个附加字段  _**：EventTimestamp**_ 和 _**Status**_。</span><span class="sxs-lookup"><span data-stu-id="e5c44-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device OData API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
>- <span data-ttu-id="e5c44-331">响应中可能会返回其他一些列。</span><span class="sxs-lookup"><span data-stu-id="e5c44-331">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="e5c44-332">这些列是临时的，可能会被删除，因此请仅使用记录列。</span><span class="sxs-lookup"><span data-stu-id="e5c44-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
>- <span data-ttu-id="e5c44-333">下表中定义的属性按字母顺序按属性 ID 列出。</span><span class="sxs-lookup"><span data-stu-id="e5c44-333">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="e5c44-334">运行此 API 时，生成的输出不必按此表中列出的相同顺序返回。</span><span class="sxs-lookup"><span data-stu-id="e5c44-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br><br/>

<span data-ttu-id="e5c44-335">属性 (ID) </span><span class="sxs-lookup"><span data-stu-id="e5c44-335">Property (ID)</span></span> | <span data-ttu-id="e5c44-336">数据类型</span><span class="sxs-lookup"><span data-stu-id="e5c44-336">Data type</span></span> | <span data-ttu-id="e5c44-337">说明</span><span class="sxs-lookup"><span data-stu-id="e5c44-337">Description</span></span> | <span data-ttu-id="e5c44-338">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="e5c44-339">CveId</span><span class="sxs-lookup"><span data-stu-id="e5c44-339">CveId</span></span> | <span data-ttu-id="e5c44-340">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-340">string</span></span> | <span data-ttu-id="e5c44-341">分配给 CVE 安全机制中常见漏洞和 (漏洞) 标识符。</span><span class="sxs-lookup"><span data-stu-id="e5c44-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="e5c44-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="e5c44-342">CVE-2020-15992</span></span>  
<span data-ttu-id="e5c44-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="e5c44-343">CvssScore</span></span> | <span data-ttu-id="e5c44-344">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-344">string</span></span> | <span data-ttu-id="e5c44-345">CVE 的 CVSS 分数。</span><span class="sxs-lookup"><span data-stu-id="e5c44-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="e5c44-346">6.2</span><span class="sxs-lookup"><span data-stu-id="e5c44-346">6.2</span></span>  
<span data-ttu-id="e5c44-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="e5c44-347">DeviceId</span></span> | <span data-ttu-id="e5c44-348">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-348">string</span></span> | <span data-ttu-id="e5c44-349">服务中设备的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e5c44-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="e5c44-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="e5c44-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="e5c44-351">DeviceName</span><span class="sxs-lookup"><span data-stu-id="e5c44-351">DeviceName</span></span> | <span data-ttu-id="e5c44-352">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-352">string</span></span> | <span data-ttu-id="e5c44-353">设备的完全限定 (FQDN) FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5c44-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="e5c44-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e5c44-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="e5c44-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="e5c44-355">DiskPaths</span></span> | <span data-ttu-id="e5c44-356">Array[string]</span><span class="sxs-lookup"><span data-stu-id="e5c44-356">Array[string]</span></span> | <span data-ttu-id="e5c44-357">表明产品已安装在设备的磁盘证据。</span><span class="sxs-lookup"><span data-stu-id="e5c44-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="e5c44-358">[ "C：\Program Files (x86) \Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="e5c44-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="e5c44-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="e5c44-359">EventTimestamp</span></span> | <span data-ttu-id="e5c44-360">String</span><span class="sxs-lookup"><span data-stu-id="e5c44-360">String</span></span> | <span data-ttu-id="e5c44-361">找到此 delta 事件的时间。</span><span class="sxs-lookup"><span data-stu-id="e5c44-361">The time this delta event was found.</span></span> | <span data-ttu-id="e5c44-362">2021-01-11T11：06：08.291Z</span><span class="sxs-lookup"><span data-stu-id="e5c44-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="e5c44-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="e5c44-363">ExploitabilityLevel</span></span> | <span data-ttu-id="e5c44-364">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-364">string</span></span> | <span data-ttu-id="e5c44-365">此漏洞的利用级别 (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) </span><span class="sxs-lookup"><span data-stu-id="e5c44-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="e5c44-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="e5c44-366">ExploitIsInKit</span></span>  
<span data-ttu-id="e5c44-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="e5c44-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="e5c44-368">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-368">string</span></span> | <span data-ttu-id="e5c44-369">首次在设备上看到此产品的 CVE 时。</span><span class="sxs-lookup"><span data-stu-id="e5c44-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="e5c44-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="e5c44-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="e5c44-371">Id</span><span class="sxs-lookup"><span data-stu-id="e5c44-371">Id</span></span> | <span data-ttu-id="e5c44-372">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-372">string</span></span> | <span data-ttu-id="e5c44-373">记录的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e5c44-373">Unique identifier for the record.</span></span> | <span data-ttu-id="e5c44-374">123ABG55_573AG&mnp！</span><span class="sxs-lookup"><span data-stu-id="e5c44-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="e5c44-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="e5c44-375">LastSeenTimestamp</span></span> | <span data-ttu-id="e5c44-376">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-376">string</span></span> | <span data-ttu-id="e5c44-377">上次在设备上看到 CVE 的时间。</span><span class="sxs-lookup"><span data-stu-id="e5c44-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="e5c44-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="e5c44-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="e5c44-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="e5c44-379">OSPlatform</span></span> | <span data-ttu-id="e5c44-380">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-380">string</span></span> | <span data-ttu-id="e5c44-381">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="e5c44-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e5c44-382">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="e5c44-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="e5c44-383">有关详细信息，请参阅 tvm 支持的操作系统和平台。</span><span class="sxs-lookup"><span data-stu-id="e5c44-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="e5c44-384">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e5c44-384">Windows10</span></span>  
<span data-ttu-id="e5c44-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="e5c44-385">RbacGroupName</span></span> | <span data-ttu-id="e5c44-386">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-386">string</span></span> | <span data-ttu-id="e5c44-387">基于角色的访问控制 (RBAC) 组。</span><span class="sxs-lookup"><span data-stu-id="e5c44-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="e5c44-388">如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。</span><span class="sxs-lookup"><span data-stu-id="e5c44-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="e5c44-389">如果组织不包含任何 RBAC 组，则值为"None"。</span><span class="sxs-lookup"><span data-stu-id="e5c44-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="e5c44-390">服务器</span><span class="sxs-lookup"><span data-stu-id="e5c44-390">Servers</span></span>  
<span data-ttu-id="e5c44-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="e5c44-391">RecommendationReference</span></span> | <span data-ttu-id="e5c44-392">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-392">string</span></span> | <span data-ttu-id="e5c44-393">对此软件相关建议 ID 的引用。</span><span class="sxs-lookup"><span data-stu-id="e5c44-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="e5c44-394">va--microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="e5c44-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="e5c44-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="e5c44-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="e5c44-396">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-396">string</span></span> | <span data-ttu-id="e5c44-397">软件供应商提供的用于解决漏洞的安全更新的名称或说明。</span><span class="sxs-lookup"><span data-stu-id="e5c44-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="e5c44-398">2020 年 4 月安全更新</span><span class="sxs-lookup"><span data-stu-id="e5c44-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="e5c44-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="e5c44-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="e5c44-400">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-400">string</span></span> | <span data-ttu-id="e5c44-401">相应指南或知识库的适用安全更新或标识符的标识符 (KB) 文章</span><span class="sxs-lookup"><span data-stu-id="e5c44-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="e5c44-402">4550961</span><span class="sxs-lookup"><span data-stu-id="e5c44-402">4550961</span></span>  
<span data-ttu-id="e5c44-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="e5c44-403">RegistryPaths</span></span>  | <span data-ttu-id="e5c44-404">Array[string]</span><span class="sxs-lookup"><span data-stu-id="e5c44-404">Array[string]</span></span> | <span data-ttu-id="e5c44-405">注册表证据，表明产品已安装在设备中。</span><span class="sxs-lookup"><span data-stu-id="e5c44-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="e5c44-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span><span class="sxs-lookup"><span data-stu-id="e5c44-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="e5c44-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="e5c44-407">SoftwareName</span></span> | <span data-ttu-id="e5c44-408">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-408">string</span></span> | <span data-ttu-id="e5c44-409">软件产品的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c44-409">Name of the software product.</span></span> | <span data-ttu-id="e5c44-410">chrome</span><span class="sxs-lookup"><span data-stu-id="e5c44-410">chrome</span></span>  
<span data-ttu-id="e5c44-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="e5c44-411">SoftwareVendor</span></span> | <span data-ttu-id="e5c44-412">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-412">string</span></span> | <span data-ttu-id="e5c44-413">软件供应商的名称。</span><span class="sxs-lookup"><span data-stu-id="e5c44-413">Name of the software vendor.</span></span> | <span data-ttu-id="e5c44-414">google</span><span class="sxs-lookup"><span data-stu-id="e5c44-414">google</span></span>  
<span data-ttu-id="e5c44-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="e5c44-415">SoftwareVersion</span></span> | <span data-ttu-id="e5c44-416">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-416">string</span></span> | <span data-ttu-id="e5c44-417">软件产品的版本号。</span><span class="sxs-lookup"><span data-stu-id="e5c44-417">Version number of the software product.</span></span> | <span data-ttu-id="e5c44-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="e5c44-418">81.0.4044.138</span></span>  
<span data-ttu-id="e5c44-419">状态</span><span class="sxs-lookup"><span data-stu-id="e5c44-419">Status</span></span> | <span data-ttu-id="e5c44-420">String</span><span class="sxs-lookup"><span data-stu-id="e5c44-420">String</span></span> | <span data-ttu-id="e5c44-421">**新建**   (如果设备上不再存在此漏洞（这意味着已修复此漏洞)  (1) **修复** (，则说明在设备上引入的新漏洞  ) 。</span><span class="sxs-lookup"><span data-stu-id="e5c44-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="e5c44-422"> (2) 更新 (如果设备上\ \*\*\**   漏洞已更改。</span><span class="sxs-lookup"><span data-stu-id="e5c44-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="e5c44-423">可能的更改包括：CVSS 分数、攻击性级别、严重性级别、DiskPaths、RegistryPaths、RecommendedSecurityUpdate) 。</span><span class="sxs-lookup"><span data-stu-id="e5c44-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="e5c44-424">Fixed</span><span class="sxs-lookup"><span data-stu-id="e5c44-424">Fixed</span></span>
<span data-ttu-id="e5c44-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="e5c44-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="e5c44-426">string</span><span class="sxs-lookup"><span data-stu-id="e5c44-426">string</span></span> | <span data-ttu-id="e5c44-427">根据 CVSS 分数和受威胁环境影响的动态因素为安全漏洞分配的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="e5c44-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="e5c44-428">中</span><span class="sxs-lookup"><span data-stu-id="e5c44-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="e5c44-429">说明</span><span class="sxs-lookup"><span data-stu-id="e5c44-429">Clarifications</span></span>

- <span data-ttu-id="e5c44-430">如果软件从版本 1.0 更新到版本 2.0，并且这两个版本都向 CVE-A 公开，您将收到 2 个单独的事件：</span><span class="sxs-lookup"><span data-stu-id="e5c44-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   1. <span data-ttu-id="e5c44-431">修复 – 1.0 版上的 CVE-A 已修复</span><span class="sxs-lookup"><span data-stu-id="e5c44-431">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   1. <span data-ttu-id="e5c44-432">新增 - 2.0 版上的 CVE-A 已添加</span><span class="sxs-lookup"><span data-stu-id="e5c44-432">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="e5c44-433">如果特定漏洞 (例如，CVE-A) 在 (特定时间首次看到，例如，) 年 1 月 10 日针对 1.0 版软件，而该软件在几天之后更新到版本 2.0（也向同一 CVE-A 公开）时，您将收到以下两个分开的事件：</span><span class="sxs-lookup"><span data-stu-id="e5c44-433">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   1. <span data-ttu-id="e5c44-434">Fixed – CVE-X，FirstSeenTimestamp January 10，version 1，0。</span><span class="sxs-lookup"><span data-stu-id="e5c44-434">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   1. <span data-ttu-id="e5c44-435">新增 – CVE-X、FirstSeenTimestamp 1 月 10 日版本 2.0。</span><span class="sxs-lookup"><span data-stu-id="e5c44-435">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="e5c44-436">3.6 示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-436">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="e5c44-437">3.6.1 请求示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-437">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="e5c44-438">3.6.2 响应示例</span><span class="sxs-lookup"><span data-stu-id="e5c44-438">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="e5c44-439">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5c44-439">See also</span></span>

- [<span data-ttu-id="e5c44-440">导出每个设备的评估方法和属性</span><span class="sxs-lookup"><span data-stu-id="e5c44-440">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="e5c44-441">导出每个设备的安全配置评估</span><span class="sxs-lookup"><span data-stu-id="e5c44-441">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="e5c44-442">导出每个设备的软件清单评估</span><span class="sxs-lookup"><span data-stu-id="e5c44-442">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="e5c44-443">其他相关</span><span class="sxs-lookup"><span data-stu-id="e5c44-443">Other related</span></span>

- [<span data-ttu-id="e5c44-444">基于风险的威胁& 漏洞管理</span><span class="sxs-lookup"><span data-stu-id="e5c44-444">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="e5c44-445">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="e5c44-445">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
