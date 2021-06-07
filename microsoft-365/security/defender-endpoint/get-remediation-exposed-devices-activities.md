---
title: 列出修正活动的暴露设备
description: 返回有关指定修正任务的公开设备的信息。
keywords: api， 修正， 修正 api， 获取， 修正任务， 修正公开的设备
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772157"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="a878e-104">列出修正活动的暴露设备</span><span class="sxs-lookup"><span data-stu-id="a878e-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a878e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a878e-105">**Applies to:**</span></span>

- [<span data-ttu-id="a878e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a878e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a878e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a878e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a878e-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a878e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a878e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a878e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="a878e-110">API 说明</span><span class="sxs-lookup"><span data-stu-id="a878e-110">API Description</span></span>

<span data-ttu-id="a878e-111">返回有关指定修正任务的公开设备的信息。</span><span class="sxs-lookup"><span data-stu-id="a878e-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="a878e-112">[详细了解修正活动](tvm-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="a878e-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="a878e-113">列出与修正任务关联的公开设备 (id) </span><span class="sxs-lookup"><span data-stu-id="a878e-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="a878e-114">**URL：** GET： /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="a878e-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="a878e-115">权限</span><span class="sxs-lookup"><span data-stu-id="a878e-115">Permissions</span></span>

<span data-ttu-id="a878e-116">若要调用此 API，需要以下权限之一。</span><span class="sxs-lookup"><span data-stu-id="a878e-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a878e-117">若要了解详细信息（包括如何选择权限），请参阅使用 [Microsoft Defender for Endpoint API 了解详细信息。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a878e-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="a878e-118">权限类型</span><span class="sxs-lookup"><span data-stu-id="a878e-118">Permission type</span></span> | <span data-ttu-id="a878e-119">权限</span><span class="sxs-lookup"><span data-stu-id="a878e-119">Permission</span></span> | <span data-ttu-id="a878e-120">权限显示名称</span><span class="sxs-lookup"><span data-stu-id="a878e-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a878e-121">应用程序</span><span class="sxs-lookup"><span data-stu-id="a878e-121">Application</span></span> | <span data-ttu-id="a878e-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="a878e-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="a878e-123">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="a878e-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="a878e-124">委派（工作或学校帐户）</span><span class="sxs-lookup"><span data-stu-id="a878e-124">Delegated (work or school account)</span></span> | <span data-ttu-id="a878e-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="a878e-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="a878e-126">\'阅读威胁和漏洞管理漏洞信息\'</span><span class="sxs-lookup"><span data-stu-id="a878e-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="a878e-127">属性详细信息</span><span class="sxs-lookup"><span data-stu-id="a878e-127">Properties details</span></span>

<span data-ttu-id="a878e-128">属性 (id) </span><span class="sxs-lookup"><span data-stu-id="a878e-128">Property (id)</span></span> | <span data-ttu-id="a878e-129">数据类型</span><span class="sxs-lookup"><span data-stu-id="a878e-129">Data type</span></span> | <span data-ttu-id="a878e-130">说明</span><span class="sxs-lookup"><span data-stu-id="a878e-130">Description</span></span> | <span data-ttu-id="a878e-131">示例</span><span class="sxs-lookup"><span data-stu-id="a878e-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="a878e-132">id</span><span class="sxs-lookup"><span data-stu-id="a878e-132">id</span></span> | <span data-ttu-id="a878e-133">String</span><span class="sxs-lookup"><span data-stu-id="a878e-133">String</span></span> | <span data-ttu-id="a878e-134">设备 ID</span><span class="sxs-lookup"><span data-stu-id="a878e-134">Device ID</span></span> | <span data-ttu-id="a878e-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="a878e-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="a878e-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="a878e-136">computerDnsName</span></span> | <span data-ttu-id="a878e-137">String</span><span class="sxs-lookup"><span data-stu-id="a878e-137">String</span></span> | <span data-ttu-id="a878e-138">设备名称</span><span class="sxs-lookup"><span data-stu-id="a878e-138">Device name</span></span> | <span data-ttu-id="a878e-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="a878e-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="a878e-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="a878e-140">osPlatform</span></span> | <span data-ttu-id="a878e-141">String</span><span class="sxs-lookup"><span data-stu-id="a878e-141">String</span></span> | <span data-ttu-id="a878e-142">设备操作系统</span><span class="sxs-lookup"><span data-stu-id="a878e-142">Device operating system</span></span> | <span data-ttu-id="a878e-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="a878e-143">WindowsServer2012R2</span></span>
<span data-ttu-id="a878e-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="a878e-144">rbacGroupName</span></span> | <span data-ttu-id="a878e-145">String</span><span class="sxs-lookup"><span data-stu-id="a878e-145">String</span></span> | <span data-ttu-id="a878e-146">与此设备关联的设备组的名称</span><span class="sxs-lookup"><span data-stu-id="a878e-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="a878e-147">服务器</span><span class="sxs-lookup"><span data-stu-id="a878e-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="a878e-148">示例</span><span class="sxs-lookup"><span data-stu-id="a878e-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="a878e-149">请求示例</span><span class="sxs-lookup"><span data-stu-id="a878e-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="a878e-150">响应示例</span><span class="sxs-lookup"><span data-stu-id="a878e-150">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="a878e-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a878e-151">See also</span></span>

- [<span data-ttu-id="a878e-152">修正方法和属性</span><span class="sxs-lookup"><span data-stu-id="a878e-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="a878e-153">按 ID 获取一个修正活动</span><span class="sxs-lookup"><span data-stu-id="a878e-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="a878e-154">列出所有修正活动</span><span class="sxs-lookup"><span data-stu-id="a878e-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="a878e-155">基于风险的威胁& 漏洞管理</span><span class="sxs-lookup"><span data-stu-id="a878e-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="a878e-156">组织中漏洞</span><span class="sxs-lookup"><span data-stu-id="a878e-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
