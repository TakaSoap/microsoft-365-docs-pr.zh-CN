---
title: 使用正确的设置扩展高级搜寻范围
description: 检查 Windows 设备上审核设置和其他设置，以帮助确保你在高级搜寻中获得最全面的数据
keywords: 高级搜寻， 事件， 透视， 实体， 审核设置， 用户帐户管理， 安全组管理， 威胁搜寻， 网络威胁搜寻， 搜索， 查询， 遥测， mdatp， Microsoft Defender ATP， Microsoft Defender for Endpoint， Windows Defender， Windows Defender ATP， Windows Defender 高级威胁防护
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500619"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="62e81-104">使用正确的设置扩展高级搜寻范围</span><span class="sxs-lookup"><span data-stu-id="62e81-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="62e81-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="62e81-105">**Applies to:**</span></span>
- [<span data-ttu-id="62e81-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="62e81-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="62e81-107">[高级](advanced-hunting-overview.md) 搜寻依赖于来自整个组织的数据。</span><span class="sxs-lookup"><span data-stu-id="62e81-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="62e81-108">若要尽可能获取最全面的数据，请确保在相应的数据源中具有正确的设置。</span><span class="sxs-lookup"><span data-stu-id="62e81-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="62e81-109">Windows 设备上的高级安全审核</span><span class="sxs-lookup"><span data-stu-id="62e81-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="62e81-110">打开这些高级审核设置，以确保获取有关设备上活动的数据，包括本地帐户管理、本地安全组管理和服务创建。</span><span class="sxs-lookup"><span data-stu-id="62e81-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="62e81-111">Data</span><span class="sxs-lookup"><span data-stu-id="62e81-111">Data</span></span> | <span data-ttu-id="62e81-112">说明</span><span class="sxs-lookup"><span data-stu-id="62e81-112">Description</span></span> | <span data-ttu-id="62e81-113">架构表</span><span class="sxs-lookup"><span data-stu-id="62e81-113">Schema table</span></span> | <span data-ttu-id="62e81-114">如何配置</span><span class="sxs-lookup"><span data-stu-id="62e81-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="62e81-115">帐户管理</span><span class="sxs-lookup"><span data-stu-id="62e81-115">Account management</span></span> | <span data-ttu-id="62e81-116">捕获为指示本地帐户创建、删除和其他与帐户相关的活动 `ActionType` 的各种值的事件</span><span class="sxs-lookup"><span data-stu-id="62e81-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="62e81-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="62e81-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="62e81-118">- 部署高级安全审核策略 [：审核用户帐户管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="62e81-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="62e81-119">- [了解高级安全审核策略](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="62e81-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="62e81-120">安全组管理</span><span class="sxs-lookup"><span data-stu-id="62e81-120">Security group management</span></span> | <span data-ttu-id="62e81-121">捕获为指示本地安全组创建和其他本地组管理活动 `ActionType` 的各种值的事件</span><span class="sxs-lookup"><span data-stu-id="62e81-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="62e81-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="62e81-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="62e81-123">- 部署高级安全审核策略： [审核安全组管理](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="62e81-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="62e81-124">- [了解高级安全审核策略](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="62e81-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="62e81-125">服务安装</span><span class="sxs-lookup"><span data-stu-id="62e81-125">Service installation</span></span> | <span data-ttu-id="62e81-126">使用 值 捕获的事件 `ActionType` `ServiceInstalled` ，指示已创建服务</span><span class="sxs-lookup"><span data-stu-id="62e81-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="62e81-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="62e81-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="62e81-128">- 部署高级安全审核策略： [审核安全系统扩展](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="62e81-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="62e81-129">- [了解高级安全审核策略](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="62e81-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="62e81-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="62e81-130">Related topics</span></span>

- [<span data-ttu-id="62e81-131">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="62e81-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="62e81-132">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="62e81-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="62e81-133">了解架构</span><span class="sxs-lookup"><span data-stu-id="62e81-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="62e81-134">处理查询结果</span><span class="sxs-lookup"><span data-stu-id="62e81-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="62e81-135">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="62e81-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="62e81-136">自定义检测概述</span><span class="sxs-lookup"><span data-stu-id="62e81-136">Custom detections overview</span></span>](overview-custom-detections.md)
