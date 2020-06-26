---
title: 高级搜寻架构中的 IdentityLogonEvents 表
description: 了解高级搜寻架构的 IdentityLogonEvents 表中的 Active Directory 记录的身份验证事件
keywords: 高级搜寻、威胁搜寻、网络威胁搜寻、microsoft 威胁防护、microsoft 365、mtp、m365、搜索、查询、遥测、架构参考、kusto、表、列、数据类型、说明、IdentityLogonEvents、Azure AD、Active Directory、Azure ATP、标识
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 17e12e9095219b7ad7923f7b5664946fff6ce724
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899371"
---
# <a name="identitylogonevents"></a><span data-ttu-id="475d7-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="475d7-104">IdentityLogonEvents</span></span>

<span data-ttu-id="475d7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="475d7-105">**Applies to:**</span></span>
- <span data-ttu-id="475d7-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="475d7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="475d7-107">`IdentityLogonEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含 Azure Active Directory 和其他 Microsoft 云应用程序和服务记录的身份验证活动的相关信息。</span><span class="sxs-lookup"><span data-stu-id="475d7-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities recorded by Azure Active Directory and other Microsoft cloud apps and services.</span></span> <span data-ttu-id="475d7-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="475d7-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="475d7-109">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="475d7-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="475d7-110">列名称</span><span class="sxs-lookup"><span data-stu-id="475d7-110">Column name</span></span> | <span data-ttu-id="475d7-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="475d7-111">Data type</span></span> | <span data-ttu-id="475d7-112">说明</span><span class="sxs-lookup"><span data-stu-id="475d7-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="475d7-113">datetime</span><span class="sxs-lookup"><span data-stu-id="475d7-113">datetime</span></span> | <span data-ttu-id="475d7-114">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="475d7-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="475d7-115">string</span><span class="sxs-lookup"><span data-stu-id="475d7-115">string</span></span> | <span data-ttu-id="475d7-116">触发事件的活动类型</span><span class="sxs-lookup"><span data-stu-id="475d7-116">Type of activity that triggered the event</span></span> |
| `LogonType` | <span data-ttu-id="475d7-117">string</span><span class="sxs-lookup"><span data-stu-id="475d7-117">string</span></span> | <span data-ttu-id="475d7-118">登录会话的类型，特别是：</span><span class="sxs-lookup"><span data-stu-id="475d7-118">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="475d7-119">- **交互式**用户使用本地键盘和屏幕与计算机进行物理交互</span><span class="sxs-lookup"><span data-stu-id="475d7-119">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="475d7-120">- **远程交互（RDP）登录**-用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端与计算机进行远程交互</span><span class="sxs-lookup"><span data-stu-id="475d7-120">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="475d7-121">- **网络**-在使用 PsExec 访问计算机时或在访问计算机上的共享资源（如打印机和共享文件夹）时启动的会话</span><span class="sxs-lookup"><span data-stu-id="475d7-121">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="475d7-122">- 由计划任务启动的**批处理**会话</span><span class="sxs-lookup"><span data-stu-id="475d7-122">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="475d7-123">- **服务**-服务会话启动时启动</span><span class="sxs-lookup"><span data-stu-id="475d7-123">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="475d7-124">string</span><span class="sxs-lookup"><span data-stu-id="475d7-124">string</span></span> | <span data-ttu-id="475d7-125">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="475d7-125">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="475d7-126">string</span><span class="sxs-lookup"><span data-stu-id="475d7-126">string</span></span> | <span data-ttu-id="475d7-127">通信过程中使用的协议</span><span class="sxs-lookup"><span data-stu-id="475d7-127">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="475d7-128">string</span><span class="sxs-lookup"><span data-stu-id="475d7-128">string</span></span> | <span data-ttu-id="475d7-129">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="475d7-129">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="475d7-130">string</span><span class="sxs-lookup"><span data-stu-id="475d7-130">string</span></span> | <span data-ttu-id="475d7-131">帐户的域</span><span class="sxs-lookup"><span data-stu-id="475d7-131">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="475d7-132">string</span><span class="sxs-lookup"><span data-stu-id="475d7-132">string</span></span> | <span data-ttu-id="475d7-133">帐户的用户主体名称（UPN）</span><span class="sxs-lookup"><span data-stu-id="475d7-133">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="475d7-134">string</span><span class="sxs-lookup"><span data-stu-id="475d7-134">string</span></span> | <span data-ttu-id="475d7-135">帐户的安全标识符（SID）</span><span class="sxs-lookup"><span data-stu-id="475d7-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="475d7-136">string</span><span class="sxs-lookup"><span data-stu-id="475d7-136">string</span></span> | <span data-ttu-id="475d7-137">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="475d7-137">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="475d7-138">string</span><span class="sxs-lookup"><span data-stu-id="475d7-138">string</span></span> | <span data-ttu-id="475d7-139">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="475d7-139">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="475d7-140">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="475d7-140">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="475d7-141">string</span><span class="sxs-lookup"><span data-stu-id="475d7-141">string</span></span> | <span data-ttu-id="475d7-142">计算机的完全限定域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="475d7-142">Fully qualified domain name (FQDN) of the machine</span></span> |
| `DeviceType` | <span data-ttu-id="475d7-143">string</span><span class="sxs-lookup"><span data-stu-id="475d7-143">string</span></span> | <span data-ttu-id="475d7-144">设备类型</span><span class="sxs-lookup"><span data-stu-id="475d7-144">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="475d7-145">string</span><span class="sxs-lookup"><span data-stu-id="475d7-145">string</span></span> | <span data-ttu-id="475d7-146">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="475d7-146">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="475d7-147">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="475d7-147">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="475d7-148">string</span><span class="sxs-lookup"><span data-stu-id="475d7-148">string</span></span> | <span data-ttu-id="475d7-149">分配给终结点的 IP 地址，并在相关的网络通信过程中使用</span><span class="sxs-lookup"><span data-stu-id="475d7-149">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="475d7-150">string</span><span class="sxs-lookup"><span data-stu-id="475d7-150">string</span></span> | <span data-ttu-id="475d7-151">与事件关联的城市、国家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="475d7-151">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="475d7-152">string</span><span class="sxs-lookup"><span data-stu-id="475d7-152">string</span></span> | <span data-ttu-id="475d7-153">与终结点 IP 地址关联的 Internet 服务提供商（ISP）</span><span class="sxs-lookup"><span data-stu-id="475d7-153">Internet service provider (ISP) associated with the endpoint IP address</span></span> |

## <a name="related-topics"></a><span data-ttu-id="475d7-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="475d7-154">Related topics</span></span>
- [<span data-ttu-id="475d7-155">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="475d7-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="475d7-156">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="475d7-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="475d7-157">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="475d7-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="475d7-158">跨设备和电子邮件搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="475d7-158">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="475d7-159">了解架构</span><span class="sxs-lookup"><span data-stu-id="475d7-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="475d7-160">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="475d7-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
