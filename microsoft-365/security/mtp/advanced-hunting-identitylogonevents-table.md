---
title: 高级搜寻架构中的 IdentityLogonEvents 表
description: 了解 Active Directory 在高级搜寻架构的 IdentityLogonEvents 表中记录的身份验证事件
keywords: 高级搜寻， 威胁搜寻， 网络威胁搜寻， Microsoft 威胁防护， microsoft 365， mtp， m365， 搜索， 查询， 遥测， 架构参考， kusto， 表， 列， 数据类型， 说明， IdentityLogonEvents， Azure AD， Active Directory， Azure ATP， 标识
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 08dd78c7648126717113066e3c87b05e624f57d0
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712350"
---
# <a name="identitylogonevents"></a><span data-ttu-id="92602-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="92602-104">IdentityLogonEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="92602-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="92602-105">**Applies to:**</span></span>
- <span data-ttu-id="92602-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92602-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="92602-107">高级搜寻架构中的表包含有关通过 Microsoft Defender 捕获的通过本地 Active Directory 进行身份验证活动的信息，以及与 Microsoft Cloud App Security 捕获的 Microsoft 联机服务相关的身份验证活动 `IdentityLogonEvents` 。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="92602-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities made through your on-premises Active Directory captured by Microsoft Defender for Identity and authentication activities related to Microsoft online services captured by Microsoft Cloud App Security.</span></span> <span data-ttu-id="92602-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="92602-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="92602-109">有关事件类型的详细信息 (表) 支持的值，请使用安全中心中提供的内置 `ActionType` 架构引用。</span><span class="sxs-lookup"><span data-stu-id="92602-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference  available in the security center.</span></span>

>[!NOTE]
><span data-ttu-id="92602-110">此表涵盖 Azure Active Directory (AD) 云应用安全跟踪的登录活动，尤其是使用 ActiveSync 和其他旧协议进行交互式登录和身份验证活动。</span><span class="sxs-lookup"><span data-stu-id="92602-110">This table covers Azure Active Directory (AD) logon activities tracked by Cloud App Security, specifically interactive sign-ins and authentication activities using ActiveSync and other legacy protocols.</span></span> <span data-ttu-id="92602-111">此表中不可用的非交互式登出可在 Azure AD 审核日志。</span><span class="sxs-lookup"><span data-stu-id="92602-111">Non-interactive logons that are not available in this table can be viewed in the Azure AD audit log.</span></span> [<span data-ttu-id="92602-112">了解有关将云应用安全连接到 Microsoft 365 有关详细信息</span><span class="sxs-lookup"><span data-stu-id="92602-112">Learn more about connecting Cloud App Security to Microsoft 365</span></span>](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

<span data-ttu-id="92602-113">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="92602-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="92602-114">列名称</span><span class="sxs-lookup"><span data-stu-id="92602-114">Column name</span></span> | <span data-ttu-id="92602-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="92602-115">Data type</span></span> | <span data-ttu-id="92602-116">说明</span><span class="sxs-lookup"><span data-stu-id="92602-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="92602-117">datetime</span><span class="sxs-lookup"><span data-stu-id="92602-117">datetime</span></span> | <span data-ttu-id="92602-118">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="92602-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="92602-119">string</span><span class="sxs-lookup"><span data-stu-id="92602-119">string</span></span> | <span data-ttu-id="92602-120">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="92602-120">Type of activity that triggered the event.</span></span> <span data-ttu-id="92602-121">有关详细信息 [，请参阅门户内架构](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 参考</span><span class="sxs-lookup"><span data-stu-id="92602-121">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `LogonType` | <span data-ttu-id="92602-122">string</span><span class="sxs-lookup"><span data-stu-id="92602-122">string</span></span> | <span data-ttu-id="92602-123">登录会话的类型，具体而言：</span><span class="sxs-lookup"><span data-stu-id="92602-123">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="92602-124">- **交互** - 用户使用本地键盘和屏幕与计算机进行物理交互</span><span class="sxs-lookup"><span data-stu-id="92602-124">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="92602-125">- **远程交互式 (RDP)** 登录 - 用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端与计算机进行远程交互</span><span class="sxs-lookup"><span data-stu-id="92602-125">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="92602-126">- **网络** - 使用 PsExec 访问计算机或访问计算机上的共享资源（如打印机和共享文件夹）时启动的会话</span><span class="sxs-lookup"><span data-stu-id="92602-126">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="92602-127">- **批处理** - 由计划任务启动的会话</span><span class="sxs-lookup"><span data-stu-id="92602-127">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="92602-128">- **服务** - 服务启动时启动的会话</span><span class="sxs-lookup"><span data-stu-id="92602-128">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="92602-129">string</span><span class="sxs-lookup"><span data-stu-id="92602-129">string</span></span> | <span data-ttu-id="92602-130">执行录制的操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="92602-130">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="92602-131">string</span><span class="sxs-lookup"><span data-stu-id="92602-131">string</span></span> | <span data-ttu-id="92602-132">使用的网络协议</span><span class="sxs-lookup"><span data-stu-id="92602-132">Network protocol used</span></span> |
| `FailureReason` | <span data-ttu-id="92602-133">string</span><span class="sxs-lookup"><span data-stu-id="92602-133">string</span></span> | <span data-ttu-id="92602-134">说明所记录操作失败的原因的信息</span><span class="sxs-lookup"><span data-stu-id="92602-134">Information explaining why the recorded action failed</span></span> |
| `AccountName` | <span data-ttu-id="92602-135">string</span><span class="sxs-lookup"><span data-stu-id="92602-135">string</span></span> | <span data-ttu-id="92602-136">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="92602-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="92602-137">string</span><span class="sxs-lookup"><span data-stu-id="92602-137">string</span></span> | <span data-ttu-id="92602-138">帐户的域</span><span class="sxs-lookup"><span data-stu-id="92602-138">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="92602-139">string</span><span class="sxs-lookup"><span data-stu-id="92602-139">string</span></span> | <span data-ttu-id="92602-140">帐户 (UPN) 用户主体名称</span><span class="sxs-lookup"><span data-stu-id="92602-140">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="92602-141">string</span><span class="sxs-lookup"><span data-stu-id="92602-141">string</span></span> | <span data-ttu-id="92602-142">帐户 (SID) 安全标识符</span><span class="sxs-lookup"><span data-stu-id="92602-142">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="92602-143">string</span><span class="sxs-lookup"><span data-stu-id="92602-143">string</span></span> | <span data-ttu-id="92602-144">Azure AD 中帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="92602-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="92602-145">string</span><span class="sxs-lookup"><span data-stu-id="92602-145">string</span></span> | <span data-ttu-id="92602-146">通讯簿中显示的帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="92602-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="92602-147">通常，给定或名字、中间初始和姓氏或姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="92602-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="92602-148">string</span><span class="sxs-lookup"><span data-stu-id="92602-148">string</span></span> | <span data-ttu-id="92602-149">设备的 FQDN (完全) 域名</span><span class="sxs-lookup"><span data-stu-id="92602-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="92602-150">string</span><span class="sxs-lookup"><span data-stu-id="92602-150">string</span></span> | <span data-ttu-id="92602-151">设备类型</span><span class="sxs-lookup"><span data-stu-id="92602-151">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="92602-152">string</span><span class="sxs-lookup"><span data-stu-id="92602-152">string</span></span> | <span data-ttu-id="92602-153">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="92602-153">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="92602-154">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="92602-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="92602-155">string</span><span class="sxs-lookup"><span data-stu-id="92602-155">string</span></span> | <span data-ttu-id="92602-156">分配给终结点的 IP 地址，在相关网络通信期间使用</span><span class="sxs-lookup"><span data-stu-id="92602-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="92602-157">string</span><span class="sxs-lookup"><span data-stu-id="92602-157">string</span></span> | <span data-ttu-id="92602-158">通信期间使用的 TCP 端口</span><span class="sxs-lookup"><span data-stu-id="92602-158">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="92602-159">string</span><span class="sxs-lookup"><span data-stu-id="92602-159">string</span></span> | <span data-ttu-id="92602-160">运行处理所记录操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="92602-160">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="92602-161">string</span><span class="sxs-lookup"><span data-stu-id="92602-161">string</span></span> | <span data-ttu-id="92602-162">运行处理所记录操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="92602-162">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="92602-163">string</span><span class="sxs-lookup"><span data-stu-id="92602-163">string</span></span> | <span data-ttu-id="92602-164">相关网络通信的目标端口</span><span class="sxs-lookup"><span data-stu-id="92602-164">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="92602-165">string</span><span class="sxs-lookup"><span data-stu-id="92602-165">string</span></span> | <span data-ttu-id="92602-166">已记录 (设备的 FQDN) 的完全限定域名</span><span class="sxs-lookup"><span data-stu-id="92602-166">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="92602-167">string</span><span class="sxs-lookup"><span data-stu-id="92602-167">string</span></span> | <span data-ttu-id="92602-168">记录的操作应用于的帐户的显示名称</span><span class="sxs-lookup"><span data-stu-id="92602-168">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="92602-169">string</span><span class="sxs-lookup"><span data-stu-id="92602-169">string</span></span> | <span data-ttu-id="92602-170">与事件关联的城市、国家/地区或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="92602-170">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="92602-171">string</span><span class="sxs-lookup"><span data-stu-id="92602-171">string</span></span> | <span data-ttu-id="92602-172">Internet 服务提供商 (ISP) 与终结点 IP 地址关联</span><span class="sxs-lookup"><span data-stu-id="92602-172">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="92602-173">long</span><span class="sxs-lookup"><span data-stu-id="92602-173">long</span></span> | <span data-ttu-id="92602-174">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="92602-174">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="92602-175">string</span><span class="sxs-lookup"><span data-stu-id="92602-175">string</span></span> | <span data-ttu-id="92602-176">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="92602-176">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="92602-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="92602-177">Related topics</span></span>
- [<span data-ttu-id="92602-178">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="92602-178">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="92602-179">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="92602-179">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="92602-180">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="92602-180">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="92602-181">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="92602-181">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="92602-182">了解架构</span><span class="sxs-lookup"><span data-stu-id="92602-182">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="92602-183">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="92602-183">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
