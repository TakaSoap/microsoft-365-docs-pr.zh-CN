---
title: 导出每个设备的软件清单评估
description: 返回一个表，该表包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 每个唯一组合的条目。
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
ms.openlocfilehash: 5663a17de2e601c506b4d1b9ac44eaab6ae6245f
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689185"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="6671e-104">导出每个设备的软件清单评估</span><span class="sxs-lookup"><span data-stu-id="6671e-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6671e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6671e-105">**Applies to:**</span></span>

- [<span data-ttu-id="6671e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6671e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6671e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6671e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6671e-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6671e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6671e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6671e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="6671e-110">不同的 API 调用用于获取不同类型的数据。</span><span class="sxs-lookup"><span data-stu-id="6671e-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="6671e-111">由于数据量可能非常大，因此有两种方法可以检索数据：</span><span class="sxs-lookup"><span data-stu-id="6671e-111">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="6671e-112">[导出软件清单评估 **OData**](#1-export-software-inventory-assessment-odata) API 按照 OData 协议提取组织的所有数据作为 Json 响应。</span><span class="sxs-lookup"><span data-stu-id="6671e-112">[Export software inventory assessment **OData**](#1-export-software-inventory-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="6671e-113">此方法最适合使用少于 _100 K_ 设备的小组织。</span><span class="sxs-lookup"><span data-stu-id="6671e-113">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="6671e-114">响应会分页，因此您可以使用响应中的 \@ odata.nextLink 字段获取下一个结果。</span><span class="sxs-lookup"><span data-stu-id="6671e-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="6671e-115">[通过文件导出 **软件清单评估**](#2-export-software-inventory-assessment-via-files)  此 API 解决方案允许更快、更可靠地提取大量数据。</span><span class="sxs-lookup"><span data-stu-id="6671e-115">[Export software inventory assessment **via files**](#2-export-software-inventory-assessment-via-files)  This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="6671e-116">因此，建议拥有 100 K 以上设备的大型组织使用。</span><span class="sxs-lookup"><span data-stu-id="6671e-116">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="6671e-117">此 API 将组织的所有数据提取为下载文件。</span><span class="sxs-lookup"><span data-stu-id="6671e-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="6671e-118">该响应包含从网站下载所有数据的Azure 存储。</span><span class="sxs-lookup"><span data-stu-id="6671e-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="6671e-119">此 API 使你能够按如下方式从Azure 存储数据：</span><span class="sxs-lookup"><span data-stu-id="6671e-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="6671e-120">调用 API 获取包含所有组织数据的下载 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="6671e-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="6671e-121">使用下载 URL 下载所有文件并处理您喜欢的数据。</span><span class="sxs-lookup"><span data-stu-id="6671e-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="6671e-122">使用 _OData_ 或 (文件收集的数据) 当前状态的当前快照，不包含历史数据。</span><span class="sxs-lookup"><span data-stu-id="6671e-122">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="6671e-123">为了收集历史数据，客户必须将数据保存在自己的数据存储中。</span><span class="sxs-lookup"><span data-stu-id="6671e-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="6671e-124">除非另有说明，否则列出的所有导出评估方法都是 \*\*\*\* 完全导出 (\*\*\*\* 也称作按设备 **_) 。_**</span><span class="sxs-lookup"><span data-stu-id="6671e-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="6671e-125">1. 导出 OData (软件清单) </span><span class="sxs-lookup"><span data-stu-id="6671e-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="6671e-126">1.1 API 方法说明</span><span class="sxs-lookup"><span data-stu-id="6671e-126">1.1 API method description</span></span>

<span data-ttu-id="6671e-127">此 API 响应包含每个设备已安装软件的所有数据。</span><span class="sxs-lookup"><span data-stu-id="6671e-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="6671e-128">返回一个表，该表包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 每个唯一组合的条目。</span><span class="sxs-lookup"><span data-stu-id="6671e-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="6671e-129">限制</span><span class="sxs-lookup"><span data-stu-id="6671e-129">Limitations</span></span>

- <span data-ttu-id="6671e-130">最大页面大小为 200，000。</span><span class="sxs-lookup"><span data-stu-id="6671e-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="6671e-131">此 API 的速率限制是每分钟 30 个调用和每小时 1000 个调用。</span><span class="sxs-lookup"><span data-stu-id="6671e-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="6671e-132">1.2 权限</span><span class="sxs-lookup"><span data-stu-id="6671e-132">1.2 Permissions</span></span>

<span data-ttu-id="6671e-133">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="6671e-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6671e-134">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6671e-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="6671e-135">权限类型</span><span class="sxs-lookup"><span data-stu-id="6671e-135">Permission type</span></span> | <span data-ttu-id="6671e-136">权限</span><span class="sxs-lookup"><span data-stu-id="6671e-136">Permission</span></span> | <span data-ttu-id="6671e-137">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="6671e-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="6671e-138">应用程序</span><span class="sxs-lookup"><span data-stu-id="6671e-138">Application</span></span> | <span data-ttu-id="6671e-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="6671e-139">Software.Read.All</span></span> | <span data-ttu-id="6671e-140">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="6671e-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="6671e-141">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="6671e-141">Delegated (work or school account)</span></span> | <span data-ttu-id="6671e-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="6671e-142">Software.Read</span></span> | <span data-ttu-id="6671e-143">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="6671e-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="6671e-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="6671e-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="6671e-145">1.4 参数</span><span class="sxs-lookup"><span data-stu-id="6671e-145">1.4 Parameters</span></span>

- <span data-ttu-id="6671e-146">pageSize (默认值 = 50，000) – 响应中的结果数。</span><span class="sxs-lookup"><span data-stu-id="6671e-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="6671e-147">$top – 要返回 (的结果数不会返回 @odata.nextLink，因此不会拉取所有) </span><span class="sxs-lookup"><span data-stu-id="6671e-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="6671e-148">1.5 属性</span><span class="sxs-lookup"><span data-stu-id="6671e-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="6671e-149">-每条记录大约包含 0.5KB 的数据。</span><span class="sxs-lookup"><span data-stu-id="6671e-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="6671e-150">在选择正确的 pageSize 参数时，您应当考虑到这一点。</span><span class="sxs-lookup"><span data-stu-id="6671e-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="6671e-151">-下表中定义的属性按字母顺序按属性 ID 列出。</span><span class="sxs-lookup"><span data-stu-id="6671e-151">-The properties defined in the following table are listed alphabetically, by property ID.</span></span> <span data-ttu-id="6671e-152">运行此 API 时，生成的输出不必按此表中列出的相同顺序返回。</span><span class="sxs-lookup"><span data-stu-id="6671e-152">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
><span data-ttu-id="6671e-153">-响应中可能会返回其他一些列。</span><span class="sxs-lookup"><span data-stu-id="6671e-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="6671e-154">这些列是临时的，可能会被删除，请仅使用记录列。</span><span class="sxs-lookup"><span data-stu-id="6671e-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="6671e-155">属性 (ID) </span><span class="sxs-lookup"><span data-stu-id="6671e-155">Property (ID)</span></span> | <span data-ttu-id="6671e-156">数据类型</span><span class="sxs-lookup"><span data-stu-id="6671e-156">Data type</span></span> | <span data-ttu-id="6671e-157">说明</span><span class="sxs-lookup"><span data-stu-id="6671e-157">Description</span></span> | <span data-ttu-id="6671e-158">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="6671e-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="6671e-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="6671e-159">DeviceId</span></span> | <span data-ttu-id="6671e-160">string</span><span class="sxs-lookup"><span data-stu-id="6671e-160">string</span></span> | <span data-ttu-id="6671e-161">服务中设备的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6671e-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="6671e-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="6671e-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="6671e-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="6671e-163">DeviceName</span></span> | <span data-ttu-id="6671e-164">string</span><span class="sxs-lookup"><span data-stu-id="6671e-164">string</span></span> | <span data-ttu-id="6671e-165">设备的完全限定 (FQDN) FQDN。</span><span class="sxs-lookup"><span data-stu-id="6671e-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="6671e-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6671e-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="6671e-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="6671e-167">DiskPaths</span></span> | <span data-ttu-id="6671e-168">Array[string]</span><span class="sxs-lookup"><span data-stu-id="6671e-168">Array[string]</span></span>  | <span data-ttu-id="6671e-169">表明产品已安装在设备的磁盘证据。</span><span class="sxs-lookup"><span data-stu-id="6671e-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="6671e-170">[ "C： \\Program Files (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="6671e-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="6671e-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="6671e-171">EndOfSupportDate</span></span> | <span data-ttu-id="6671e-172">string</span><span class="sxs-lookup"><span data-stu-id="6671e-172">string</span></span> | <span data-ttu-id="6671e-173">此软件支持已结束或将终止的日期。</span><span class="sxs-lookup"><span data-stu-id="6671e-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="6671e-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="6671e-174">2020-12-30</span></span>
<span data-ttu-id="6671e-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="6671e-175">EndOfSupportStatus</span></span> | <span data-ttu-id="6671e-176">string</span><span class="sxs-lookup"><span data-stu-id="6671e-176">string</span></span> | <span data-ttu-id="6671e-177">停止提供支持状态。</span><span class="sxs-lookup"><span data-stu-id="6671e-177">End of support status.</span></span> <span data-ttu-id="6671e-178">可以包含以下可能的值：None、EOS Version、Upcoming EOS Version、EOS Software、Upcoming EOS Software。</span><span class="sxs-lookup"><span data-stu-id="6671e-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="6671e-179">即将推出的 EOS</span><span class="sxs-lookup"><span data-stu-id="6671e-179">Upcoming EOS</span></span>
<span data-ttu-id="6671e-180">Id</span><span class="sxs-lookup"><span data-stu-id="6671e-180">Id</span></span> | <span data-ttu-id="6671e-181">string</span><span class="sxs-lookup"><span data-stu-id="6671e-181">string</span></span> | <span data-ttu-id="6671e-182">记录的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6671e-182">Unique identifier for the record.</span></span> | <span data-ttu-id="6671e-183">123ABG55_573AG&mnp！</span><span class="sxs-lookup"><span data-stu-id="6671e-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="6671e-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="6671e-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="6671e-185">int</span><span class="sxs-lookup"><span data-stu-id="6671e-185">int</span></span> | <span data-ttu-id="6671e-186">此设备上此软件上漏洞的数量</span><span class="sxs-lookup"><span data-stu-id="6671e-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="6671e-187">3</span><span class="sxs-lookup"><span data-stu-id="6671e-187">3</span></span>
<span data-ttu-id="6671e-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="6671e-188">OSPlatform</span></span> | <span data-ttu-id="6671e-189">string</span><span class="sxs-lookup"><span data-stu-id="6671e-189">string</span></span> | <span data-ttu-id="6671e-190">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="6671e-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6671e-191">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="6671e-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="6671e-192">有关详细信息，请参阅 tvm 支持的操作系统和平台。</span><span class="sxs-lookup"><span data-stu-id="6671e-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="6671e-193">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6671e-193">Windows10</span></span>
<span data-ttu-id="6671e-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6671e-194">RbacGroupName</span></span> | <span data-ttu-id="6671e-195">string</span><span class="sxs-lookup"><span data-stu-id="6671e-195">string</span></span> | <span data-ttu-id="6671e-196">基于角色的访问控制 (RBAC) 组。</span><span class="sxs-lookup"><span data-stu-id="6671e-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="6671e-197">如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。</span><span class="sxs-lookup"><span data-stu-id="6671e-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="6671e-198">如果组织不包含任何 RBAC 组，则值为"None"。</span><span class="sxs-lookup"><span data-stu-id="6671e-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="6671e-199">服务器</span><span class="sxs-lookup"><span data-stu-id="6671e-199">Servers</span></span>
<span data-ttu-id="6671e-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="6671e-200">RegistryPaths</span></span> | <span data-ttu-id="6671e-201">Array[string]</span><span class="sxs-lookup"><span data-stu-id="6671e-201">Array[string]</span></span> | <span data-ttu-id="6671e-202">注册表证据，表明产品已安装在设备中。</span><span class="sxs-lookup"><span data-stu-id="6671e-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="6671e-203">[ "HKEY_LOCAL_MACHINE \\SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Uninstall Microsoft \\ \\ Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="6671e-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="6671e-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="6671e-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="6671e-205">string</span><span class="sxs-lookup"><span data-stu-id="6671e-205">string</span></span> | <span data-ttu-id="6671e-206">首次在设备上看到此软件。</span><span class="sxs-lookup"><span data-stu-id="6671e-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="6671e-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="6671e-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="6671e-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="6671e-208">SoftwareName</span></span> | <span data-ttu-id="6671e-209">string</span><span class="sxs-lookup"><span data-stu-id="6671e-209">string</span></span> | <span data-ttu-id="6671e-210">软件产品的名称。</span><span class="sxs-lookup"><span data-stu-id="6671e-210">Name of the software product.</span></span> | <span data-ttu-id="6671e-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="6671e-211">Silverlight</span></span>
<span data-ttu-id="6671e-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="6671e-212">SoftwareVendor</span></span> | <span data-ttu-id="6671e-213">string</span><span class="sxs-lookup"><span data-stu-id="6671e-213">string</span></span> | <span data-ttu-id="6671e-214">软件供应商的名称。</span><span class="sxs-lookup"><span data-stu-id="6671e-214">Name of the software vendor.</span></span> | <span data-ttu-id="6671e-215">microsoft</span><span class="sxs-lookup"><span data-stu-id="6671e-215">microsoft</span></span>
<span data-ttu-id="6671e-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="6671e-216">SoftwareVersion</span></span> | <span data-ttu-id="6671e-217">string</span><span class="sxs-lookup"><span data-stu-id="6671e-217">string</span></span> | <span data-ttu-id="6671e-218">软件产品的版本号。</span><span class="sxs-lookup"><span data-stu-id="6671e-218">Version number of the software product.</span></span> | <span data-ttu-id="6671e-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="6671e-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="6671e-220">1.6 示例</span><span class="sxs-lookup"><span data-stu-id="6671e-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="6671e-221">1.6.1 请求示例</span><span class="sxs-lookup"><span data-stu-id="6671e-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="6671e-222">1.6.2 响应示例</span><span class="sxs-lookup"><span data-stu-id="6671e-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="6671e-223">2. 通过文件库导出 (清单) </span><span class="sxs-lookup"><span data-stu-id="6671e-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="6671e-224">2.1 API 方法说明</span><span class="sxs-lookup"><span data-stu-id="6671e-224">2.1 API method description</span></span>

<span data-ttu-id="6671e-225">此 API 响应包含每个设备已安装软件的所有数据。</span><span class="sxs-lookup"><span data-stu-id="6671e-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="6671e-226">返回一个表，该表包含 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion 每个唯一组合的条目。</span><span class="sxs-lookup"><span data-stu-id="6671e-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="6671e-227">2.1.1 限制</span><span class="sxs-lookup"><span data-stu-id="6671e-227">2.1.1 Limitations</span></span>

<span data-ttu-id="6671e-228">此 API 的速率限制是每分钟 5 个调用和每小时 20 个调用。</span><span class="sxs-lookup"><span data-stu-id="6671e-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="6671e-229">2.2 权限</span><span class="sxs-lookup"><span data-stu-id="6671e-229">2.2 Permissions</span></span>

<span data-ttu-id="6671e-230">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="6671e-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6671e-231">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6671e-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="6671e-232">权限类型</span><span class="sxs-lookup"><span data-stu-id="6671e-232">Permission type</span></span> | <span data-ttu-id="6671e-233">权限</span><span class="sxs-lookup"><span data-stu-id="6671e-233">Permission</span></span> | <span data-ttu-id="6671e-234">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="6671e-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="6671e-235">应用程序</span><span class="sxs-lookup"><span data-stu-id="6671e-235">Application</span></span> | <span data-ttu-id="6671e-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="6671e-236">Software.Read.All</span></span> | <span data-ttu-id="6671e-237">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="6671e-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="6671e-238">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="6671e-238">Delegated (work or school account)</span></span> | <span data-ttu-id="6671e-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="6671e-239">Software.Read</span></span> | <span data-ttu-id="6671e-240">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="6671e-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="6671e-241">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="6671e-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="6671e-242">参数</span><span class="sxs-lookup"><span data-stu-id="6671e-242">Parameters</span></span>

- <span data-ttu-id="6671e-243">sasValidHours – 下载 URL 在最长 24 小时 (的有效小时数) </span><span class="sxs-lookup"><span data-stu-id="6671e-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="6671e-244">2.5 属性</span><span class="sxs-lookup"><span data-stu-id="6671e-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="6671e-245">文件是 gzip 压缩文件& Json 格式。</span><span class="sxs-lookup"><span data-stu-id="6671e-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="6671e-246">下载 URL 的有效期仅为 3 小时。</span><span class="sxs-lookup"><span data-stu-id="6671e-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="6671e-247">否则，可以使用 参数。</span><span class="sxs-lookup"><span data-stu-id="6671e-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="6671e-248">_ 为了最大数据下载速度，你可以确保从数据所在的同一 Azure 区域进行下载。</span><span class="sxs-lookup"><span data-stu-id="6671e-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="6671e-249">属性 (ID) </span><span class="sxs-lookup"><span data-stu-id="6671e-249">Property (ID)</span></span> | <span data-ttu-id="6671e-250">数据类型</span><span class="sxs-lookup"><span data-stu-id="6671e-250">Data type</span></span> | <span data-ttu-id="6671e-251">说明</span><span class="sxs-lookup"><span data-stu-id="6671e-251">Description</span></span> | <span data-ttu-id="6671e-252">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="6671e-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="6671e-253">导出文件</span><span class="sxs-lookup"><span data-stu-id="6671e-253">Export files</span></span> | <span data-ttu-id="6671e-254">数组 \[ 字符串\]</span><span class="sxs-lookup"><span data-stu-id="6671e-254">array\[string\]</span></span> | <span data-ttu-id="6671e-255">保存组织当前快照的文件的下载 URL 列表</span><span class="sxs-lookup"><span data-stu-id="6671e-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="6671e-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="6671e-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="6671e-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="6671e-257">GeneratedTime</span></span> | <span data-ttu-id="6671e-258">string</span><span class="sxs-lookup"><span data-stu-id="6671e-258">string</span></span> | <span data-ttu-id="6671e-259">导出的生成时间。</span><span class="sxs-lookup"><span data-stu-id="6671e-259">The time that the export was generated.</span></span> | <span data-ttu-id="6671e-260">2021-05-20T08：00：00Z ]</span><span class="sxs-lookup"><span data-stu-id="6671e-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="6671e-261">2.6 示例</span><span class="sxs-lookup"><span data-stu-id="6671e-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="6671e-262">2.6.1 请求示例</span><span class="sxs-lookup"><span data-stu-id="6671e-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="6671e-263">2.6.2 响应示例</span><span class="sxs-lookup"><span data-stu-id="6671e-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="6671e-264">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6671e-264">See also</span></span>

- [<span data-ttu-id="6671e-265">导出每个设备的评估方法和属性</span><span class="sxs-lookup"><span data-stu-id="6671e-265">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="6671e-266">导出每个设备的安全配置评估</span><span class="sxs-lookup"><span data-stu-id="6671e-266">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="6671e-267">导出每个设备的软件漏洞评估</span><span class="sxs-lookup"><span data-stu-id="6671e-267">Export software vulnerabilities assessment per device</span></span>](get-assessmnt-software-vulnerabilities.md)

<span data-ttu-id="6671e-268">其他相关</span><span class="sxs-lookup"><span data-stu-id="6671e-268">Other related</span></span>

- [<span data-ttu-id="6671e-269">基于风险的威胁& 漏洞管理</span><span class="sxs-lookup"><span data-stu-id="6671e-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="6671e-270">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="6671e-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
