---
title: 导出每个设备的安全配置评估
description: 返回 DeviceId、ConfigurationId 每个唯一组合的条目。
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
ms.openlocfilehash: ad8b2030da4fb4815eb71ca53fb2dbac67a05d79
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022386"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="0ed1d-104">导出每个设备的安全配置评估</span><span class="sxs-lookup"><span data-stu-id="0ed1d-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0ed1d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0ed1d-105">**Applies to:**</span></span>

- [<span data-ttu-id="0ed1d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0ed1d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0ed1d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ed1d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0ed1d-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="0ed1d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0ed1d-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="0ed1d-110">基于每个设备返回所有配置及其状态。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="0ed1d-111">不同的 API 调用用于获取不同类型的数据。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="0ed1d-112">由于数据量可能很大，因此有两种方法可以检索数据：</span><span class="sxs-lookup"><span data-stu-id="0ed1d-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="0ed1d-113">[导出安全配置评估 **JSON 响应**](#1-export-secure-configuration-assessment-json-response)：API 提取组织的所有数据作为 Json 响应。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-113">[Export secure configuration assessment **JSON response**](#1-export-secure-configuration-assessment-json-response):  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="0ed1d-114">此方法最适合设备 _数少于 100 K_ 的小组织。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-114">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="0ed1d-115">响应会分页，因此您可以使用响应中的 \@ odata.nextLink 字段获取下一个结果。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="0ed1d-116">[通过文件 **导出安全配置评估**](#2-export-secure-configuration-assessment-via-files)：此 API 解决方案允许更快、更可靠地拉取大量数据。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="0ed1d-117">因此，建议拥有 100 K 以上设备的大型组织使用。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-117">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="0ed1d-118">此 API 将组织的所有数据提取为下载文件。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="0ed1d-119">该响应包含从网站下载所有数据的Azure 存储空间。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="0ed1d-120">通过此 API，可以从以下Azure 存储空间下载所有数据：</span><span class="sxs-lookup"><span data-stu-id="0ed1d-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="0ed1d-121">调用 API 获取包含所有组织数据的下载 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="0ed1d-122">使用下载 URL 下载所有文件并处理您喜欢的数据。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="0ed1d-123">使用 _OData_ 或 (文件收集的数据) 当前状态的当前快照，不包含历史数据。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-123">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="0ed1d-124">为了收集历史数据，客户必须将数据保存在自己的数据存储中。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="0ed1d-125">除非另有说明，否则列出的所有导出评估方法都是 \*\*\*\* 完全导出 (\*\*\*\* 也称作按设备 **_) 。_**</span><span class="sxs-lookup"><span data-stu-id="0ed1d-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-json-response"></a><span data-ttu-id="0ed1d-126">1. 导出 JSON 响应 (安全配置) </span><span class="sxs-lookup"><span data-stu-id="0ed1d-126">1. Export secure configuration assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="0ed1d-127">1.1 API 方法说明</span><span class="sxs-lookup"><span data-stu-id="0ed1d-127">1.1 API method description</span></span>

<span data-ttu-id="0ed1d-128">此 API 响应包含公开设备上的安全配置评估，并返回 DeviceId、ConfigurationId 每个唯一组合的条目。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="0ed1d-129">1.1.1 限制</span><span class="sxs-lookup"><span data-stu-id="0ed1d-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="0ed1d-130">最大页面大小为 200，000。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="0ed1d-131">此 API 的速率限制是每分钟 30 个调用和每小时 1000 个调用。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="0ed1d-132">1.2 权限</span><span class="sxs-lookup"><span data-stu-id="0ed1d-132">1.2 Permissions</span></span>

<span data-ttu-id="0ed1d-133">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0ed1d-134">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API](apis-intro.md) 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="0ed1d-135">权限类型</span><span class="sxs-lookup"><span data-stu-id="0ed1d-135">Permission type</span></span> | <span data-ttu-id="0ed1d-136">权限</span><span class="sxs-lookup"><span data-stu-id="0ed1d-136">Permission</span></span> | <span data-ttu-id="0ed1d-137">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="0ed1d-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="0ed1d-138">应用程序</span><span class="sxs-lookup"><span data-stu-id="0ed1d-138">Application</span></span> | <span data-ttu-id="0ed1d-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="0ed1d-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="0ed1d-140">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="0ed1d-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="0ed1d-141">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="0ed1d-141">Delegated (work or school account)</span></span> | <span data-ttu-id="0ed1d-142">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="0ed1d-142">Vulnerability.Read</span></span> | <span data-ttu-id="0ed1d-143">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="0ed1d-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="0ed1d-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="0ed1d-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="0ed1d-145">1.4 参数</span><span class="sxs-lookup"><span data-stu-id="0ed1d-145">1.4 Parameters</span></span>

- <span data-ttu-id="0ed1d-146">pageSize \( default = 50，000 \) – 响应中的结果数</span><span class="sxs-lookup"><span data-stu-id="0ed1d-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="0ed1d-147">\$top – 要返回的结果 \( 数不返回 \@ odata.nextLink，因此不拉取所有数据\)</span><span class="sxs-lookup"><span data-stu-id="0ed1d-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="0ed1d-148">1.5 属性</span><span class="sxs-lookup"><span data-stu-id="0ed1d-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="0ed1d-149">下表中定义的属性按字母顺序按属性 ID 列出。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="0ed1d-150">运行此 API 时，生成的输出不必按此表中列出的相同顺序返回。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="0ed1d-151">响应中可能会返回其他一些列。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="0ed1d-152">这些列是临时的，可能会被删除，请仅使用记录列。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="0ed1d-153">属性 (ID) </span><span class="sxs-lookup"><span data-stu-id="0ed1d-153">Property (ID)</span></span> | <span data-ttu-id="0ed1d-154">数据类型</span><span class="sxs-lookup"><span data-stu-id="0ed1d-154">Data type</span></span> | <span data-ttu-id="0ed1d-155">说明</span><span class="sxs-lookup"><span data-stu-id="0ed1d-155">Description</span></span> | <span data-ttu-id="0ed1d-156">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="0ed1d-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="0ed1d-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="0ed1d-157">ConfigurationCategory</span></span> | <span data-ttu-id="0ed1d-158">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-158">string</span></span> | <span data-ttu-id="0ed1d-159">配置所属的类别或分组：应用程序、OS、网络、帐户、安全控件</span><span class="sxs-lookup"><span data-stu-id="0ed1d-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="0ed1d-160">安全控件</span><span class="sxs-lookup"><span data-stu-id="0ed1d-160">Security controls</span></span>
<span data-ttu-id="0ed1d-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="0ed1d-161">ConfigurationId</span></span> | <span data-ttu-id="0ed1d-162">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-162">string</span></span> | <span data-ttu-id="0ed1d-163">特定配置的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="0ed1d-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="0ed1d-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="0ed1d-164">scid-10000</span></span>
<span data-ttu-id="0ed1d-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="0ed1d-165">ConfigurationImpact</span></span> | <span data-ttu-id="0ed1d-166">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-166">string</span></span> | <span data-ttu-id="0ed1d-167">配置对总体配置评分的影响程度 (1-10)</span><span class="sxs-lookup"><span data-stu-id="0ed1d-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="0ed1d-168">9 </span><span class="sxs-lookup"><span data-stu-id="0ed1d-168">9</span></span>
<span data-ttu-id="0ed1d-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="0ed1d-169">ConfigurationName</span></span> | <span data-ttu-id="0ed1d-170">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-170">string</span></span> | <span data-ttu-id="0ed1d-171">配置的显示名称</span><span class="sxs-lookup"><span data-stu-id="0ed1d-171">Display name of the configuration</span></span> | <span data-ttu-id="0ed1d-172">将设备载入到 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0ed1d-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="0ed1d-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="0ed1d-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="0ed1d-174">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-174">string</span></span> | <span data-ttu-id="0ed1d-175">配置所属的子类别或子组。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="0ed1d-176">在许多情况下，它用于描述特定的功能。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="0ed1d-177">载入设备</span><span class="sxs-lookup"><span data-stu-id="0ed1d-177">Onboard Devices</span></span>
<span data-ttu-id="0ed1d-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="0ed1d-178">DeviceId</span></span> | <span data-ttu-id="0ed1d-179">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-179">string</span></span> | <span data-ttu-id="0ed1d-180">服务中设备的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="0ed1d-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="0ed1d-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="0ed1d-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="0ed1d-182">DeviceName</span></span> | <span data-ttu-id="0ed1d-183">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-183">string</span></span> | <span data-ttu-id="0ed1d-184">设备的完全限定 (FQDN) FQDN。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="0ed1d-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0ed1d-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="0ed1d-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="0ed1d-186">IsApplicable</span></span> | <span data-ttu-id="0ed1d-187">bool</span><span class="sxs-lookup"><span data-stu-id="0ed1d-187">bool</span></span> | <span data-ttu-id="0ed1d-188">指示配置或策略是否适用</span><span class="sxs-lookup"><span data-stu-id="0ed1d-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="0ed1d-189">true</span><span class="sxs-lookup"><span data-stu-id="0ed1d-189">true</span></span>
<span data-ttu-id="0ed1d-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="0ed1d-190">IsCompliant</span></span> | <span data-ttu-id="0ed1d-191">bool</span><span class="sxs-lookup"><span data-stu-id="0ed1d-191">bool</span></span> | <span data-ttu-id="0ed1d-192">指示是否正确配置了配置或策略</span><span class="sxs-lookup"><span data-stu-id="0ed1d-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="0ed1d-193">false</span><span class="sxs-lookup"><span data-stu-id="0ed1d-193">false</span></span>
<span data-ttu-id="0ed1d-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="0ed1d-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="0ed1d-195">bool</span><span class="sxs-lookup"><span data-stu-id="0ed1d-195">bool</span></span> | <span data-ttu-id="0ed1d-196">指示是否将应用配置时影响用户</span><span class="sxs-lookup"><span data-stu-id="0ed1d-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="0ed1d-197">true</span><span class="sxs-lookup"><span data-stu-id="0ed1d-197">true</span></span>
<span data-ttu-id="0ed1d-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="0ed1d-198">OSPlatform</span></span> | <span data-ttu-id="0ed1d-199">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-199">string</span></span> | <span data-ttu-id="0ed1d-200">在设备上运行的操作系统的平台。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0ed1d-201">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="0ed1d-202">有关详细信息，请参阅 tvm 支持的操作系统和平台。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="0ed1d-203">Windows 10</span><span class="sxs-lookup"><span data-stu-id="0ed1d-203">Windows10</span></span>
<span data-ttu-id="0ed1d-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="0ed1d-204">RbacGroupName</span></span> | <span data-ttu-id="0ed1d-205">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-205">string</span></span> | <span data-ttu-id="0ed1d-206">基于角色的访问控制 (RBAC) 组。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="0ed1d-207">如果此设备未分配给任何 RBAC 组，则值将为"Unassigned"。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="0ed1d-208">如果组织不包含任何 RBAC 组，则值为"None"。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="0ed1d-209">服务器</span><span class="sxs-lookup"><span data-stu-id="0ed1d-209">Servers</span></span>
<span data-ttu-id="0ed1d-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="0ed1d-210">RecommendationReference</span></span> | <span data-ttu-id="0ed1d-211">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-211">string</span></span> | <span data-ttu-id="0ed1d-212">对此软件相关建议 ID 的引用。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="0ed1d-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="0ed1d-213">sca-_-scid-20000</span></span>
<span data-ttu-id="0ed1d-214">Timestamp</span><span class="sxs-lookup"><span data-stu-id="0ed1d-214">Timestamp</span></span> | <span data-ttu-id="0ed1d-215">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-215">string</span></span> | <span data-ttu-id="0ed1d-216">上次在设备上看到配置的时间</span><span class="sxs-lookup"><span data-stu-id="0ed1d-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="0ed1d-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="0ed1d-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="0ed1d-218">1.6 示例</span><span class="sxs-lookup"><span data-stu-id="0ed1d-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="0ed1d-219">1.6.1 请求示例</span><span class="sxs-lookup"><span data-stu-id="0ed1d-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="0ed1d-220">1.6.2 响应示例</span><span class="sxs-lookup"><span data-stu-id="0ed1d-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="0ed1d-221">2. 通过文件 (导出安全配置) </span><span class="sxs-lookup"><span data-stu-id="0ed1d-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="0ed1d-222">2.1 API 方法说明</span><span class="sxs-lookup"><span data-stu-id="0ed1d-222">2.1 API method description</span></span>

<span data-ttu-id="0ed1d-223">此 API 响应包含公开设备上的安全配置评估，并返回 DeviceId、ConfigurationId 每个唯一组合的条目。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="0ed1d-224">2.1.2 限制</span><span class="sxs-lookup"><span data-stu-id="0ed1d-224">2.1.2 Limitations</span></span>

<span data-ttu-id="0ed1d-225">此 API 的速率限制是每分钟 5 个调用和每小时 20 个调用。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="0ed1d-226">2.2 权限</span><span class="sxs-lookup"><span data-stu-id="0ed1d-226">2.2 Permissions</span></span>

<span data-ttu-id="0ed1d-227">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0ed1d-228">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0ed1d-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="0ed1d-229">权限类型</span><span class="sxs-lookup"><span data-stu-id="0ed1d-229">Permission type</span></span> | <span data-ttu-id="0ed1d-230">权限</span><span class="sxs-lookup"><span data-stu-id="0ed1d-230">Permission</span></span> | <span data-ttu-id="0ed1d-231">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="0ed1d-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="0ed1d-232">应用程序</span><span class="sxs-lookup"><span data-stu-id="0ed1d-232">Application</span></span> | <span data-ttu-id="0ed1d-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="0ed1d-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="0ed1d-234">\'读取"危险和漏洞管理"漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="0ed1d-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="0ed1d-235">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="0ed1d-235">Delegated (work or school account)</span></span> | <span data-ttu-id="0ed1d-236">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="0ed1d-236">Vulnerability.Read</span></span> | <span data-ttu-id="0ed1d-237">\'读取"危险和漏洞管理"漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="0ed1d-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="0ed1d-238">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="0ed1d-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="0ed1d-239">参数</span><span class="sxs-lookup"><span data-stu-id="0ed1d-239">Parameters</span></span>

- <span data-ttu-id="0ed1d-240">sasValidHours – 下载 URL 有效期为 24 小时 (24 小时) 。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="0ed1d-241">2.5 属性</span><span class="sxs-lookup"><span data-stu-id="0ed1d-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="0ed1d-242">文件是 gzip 压缩文件& Json 格式。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="0ed1d-243">下载 URL 的有效期仅为 3 小时;否则，可以使用 参数。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="0ed1d-244">为了最大限度提高数据的下载速度，你可以确保从数据所在的同一 Azure 区域进行下载。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="0ed1d-245">属性 (ID) </span><span class="sxs-lookup"><span data-stu-id="0ed1d-245">Property (ID)</span></span> | <span data-ttu-id="0ed1d-246">数据类型</span><span class="sxs-lookup"><span data-stu-id="0ed1d-246">Data type</span></span> | <span data-ttu-id="0ed1d-247">说明</span><span class="sxs-lookup"><span data-stu-id="0ed1d-247">Description</span></span> | <span data-ttu-id="0ed1d-248">返回值的示例</span><span class="sxs-lookup"><span data-stu-id="0ed1d-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="0ed1d-249">导出文件</span><span class="sxs-lookup"><span data-stu-id="0ed1d-249">Export files</span></span> | <span data-ttu-id="0ed1d-250">数组 \[ 字符串\]</span><span class="sxs-lookup"><span data-stu-id="0ed1d-250">array\[string\]</span></span> | <span data-ttu-id="0ed1d-251">保存组织当前快照的文件的下载 URL 列表</span><span class="sxs-lookup"><span data-stu-id="0ed1d-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="0ed1d-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="0ed1d-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="0ed1d-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="0ed1d-253">GeneratedTime</span></span> | <span data-ttu-id="0ed1d-254">string</span><span class="sxs-lookup"><span data-stu-id="0ed1d-254">string</span></span> | <span data-ttu-id="0ed1d-255">导出的生成时间。</span><span class="sxs-lookup"><span data-stu-id="0ed1d-255">The time that the export was generated.</span></span> | <span data-ttu-id="0ed1d-256">2021-05-20T08：00：00Z ]</span><span class="sxs-lookup"><span data-stu-id="0ed1d-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="0ed1d-257">2.6 示例</span><span class="sxs-lookup"><span data-stu-id="0ed1d-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="0ed1d-258">2.6.1 请求示例</span><span class="sxs-lookup"><span data-stu-id="0ed1d-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="0ed1d-259">2.6.2 响应示例</span><span class="sxs-lookup"><span data-stu-id="0ed1d-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="0ed1d-260">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ed1d-260">See also</span></span>

- [<span data-ttu-id="0ed1d-261">导出每个设备的评估方法和属性</span><span class="sxs-lookup"><span data-stu-id="0ed1d-261">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="0ed1d-262">导出每个设备的软件清单评估</span><span class="sxs-lookup"><span data-stu-id="0ed1d-262">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

- [<span data-ttu-id="0ed1d-263">导出每个设备的软件漏洞评估</span><span class="sxs-lookup"><span data-stu-id="0ed1d-263">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="0ed1d-264">其他相关</span><span class="sxs-lookup"><span data-stu-id="0ed1d-264">Other related</span></span>

- [<span data-ttu-id="0ed1d-265">基于风险的威胁& 漏洞管理</span><span class="sxs-lookup"><span data-stu-id="0ed1d-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="0ed1d-266">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="0ed1d-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
