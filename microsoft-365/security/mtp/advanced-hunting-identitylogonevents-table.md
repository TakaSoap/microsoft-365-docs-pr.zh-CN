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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 2ecf6de79f5eab4aca7bc928ea64b780a257b908
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412726"
---
# <a name="identitylogonevents"></a><span data-ttu-id="8a2eb-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="8a2eb-104">IdentityLogonEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8a2eb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8a2eb-105">**Applies to:**</span></span>
- <span data-ttu-id="8a2eb-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8a2eb-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8a2eb-107">`IdentityLogonEvents`[高级搜寻](advanced-hunting-overview.md)架构中的表包含通过 Azure ATP 和与 Microsoft 云应用安全捕获的 microsoft online 服务捕获的身份验证活动捕获的身份验证活动的相关信息。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities made through your on-premises Active Directory captured by Azure ATP and authentication activities related to Microsoft online services captured by Microsoft Cloud App Security.</span></span> <span data-ttu-id="8a2eb-108">使用此参考来构建从此表返回信息的查询。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="8a2eb-109">若要详细了解表支持的事件类型 (`ActionType` 值) ，请使用 "安全中心" 中提供的 [内置架构引用](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

>[!NOTE]
><span data-ttu-id="8a2eb-110">此表介绍了由云应用安全性跟踪的 Azure Active Directory (AD) 登录活动，特别是使用 ActiveSync 和其他旧协议的交互式登录和身份验证活动。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-110">This table covers Azure Active Directory (AD) logon activities tracked by Cloud App Security, specifically interactive sign-ins and authentication activities using ActiveSync and other legacy protocols.</span></span> <span data-ttu-id="8a2eb-111">可以在 Azure AD 审核日志中查看此表中不可用的非交互式登录。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-111">Non-interactive logons that are not available in this table can be viewed in the Azure AD audit log.</span></span> [<span data-ttu-id="8a2eb-112">了解有关将云应用安全连接到 Microsoft 365 的详细信息</span><span class="sxs-lookup"><span data-stu-id="8a2eb-112">Learn more about connecting Cloud App Security to Microsoft 365</span></span>](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

<span data-ttu-id="8a2eb-113">有关高级搜寻架构中其他表的信息，请[参阅高级搜寻参考](advanced-hunting-schema-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8a2eb-114">列名称</span><span class="sxs-lookup"><span data-stu-id="8a2eb-114">Column name</span></span> | <span data-ttu-id="8a2eb-115">数据类型</span><span class="sxs-lookup"><span data-stu-id="8a2eb-115">Data type</span></span> | <span data-ttu-id="8a2eb-116">说明</span><span class="sxs-lookup"><span data-stu-id="8a2eb-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8a2eb-117">datetime</span><span class="sxs-lookup"><span data-stu-id="8a2eb-117">datetime</span></span> | <span data-ttu-id="8a2eb-118">记录事件的日期和时间</span><span class="sxs-lookup"><span data-stu-id="8a2eb-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="8a2eb-119">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-119">string</span></span> | <span data-ttu-id="8a2eb-120">触发事件的活动类型。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-120">Type of activity that triggered the event.</span></span> <span data-ttu-id="8a2eb-121">有关详细信息，请参阅[在门户架构参考中](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="8a2eb-121">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `LogonType` | <span data-ttu-id="8a2eb-122">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-122">string</span></span> | <span data-ttu-id="8a2eb-123">登录会话的类型，特别是：</span><span class="sxs-lookup"><span data-stu-id="8a2eb-123">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="8a2eb-124">- **交互式** 用户使用本地键盘和屏幕与计算机进行物理交互</span><span class="sxs-lookup"><span data-stu-id="8a2eb-124">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="8a2eb-125">- **远程交互 (RDP) 登录** -用户使用远程桌面、终端服务、远程协助或其他 RDP 客户端远程与计算机交互</span><span class="sxs-lookup"><span data-stu-id="8a2eb-125">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="8a2eb-126">- **网络** -在使用 PsExec 访问计算机时或在访问计算机上的共享资源（如打印机和共享文件夹）时启动的会话</span><span class="sxs-lookup"><span data-stu-id="8a2eb-126">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="8a2eb-127">- 由计划任务启动的**批处理**会话</span><span class="sxs-lookup"><span data-stu-id="8a2eb-127">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="8a2eb-128">- **服务** -服务会话启动时启动</span><span class="sxs-lookup"><span data-stu-id="8a2eb-128">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="8a2eb-129">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-129">string</span></span> | <span data-ttu-id="8a2eb-130">执行录制操作的应用程序</span><span class="sxs-lookup"><span data-stu-id="8a2eb-130">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="8a2eb-131">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-131">string</span></span> | <span data-ttu-id="8a2eb-132">使用的网络协议</span><span class="sxs-lookup"><span data-stu-id="8a2eb-132">Network protocol used</span></span> |
| `FailureReason` | <span data-ttu-id="8a2eb-133">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-133">string</span></span> | <span data-ttu-id="8a2eb-134">解释录制的操作失败原因的信息</span><span class="sxs-lookup"><span data-stu-id="8a2eb-134">Information explaining why the recorded action failed</span></span> |
| `AccountName` | <span data-ttu-id="8a2eb-135">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-135">string</span></span> | <span data-ttu-id="8a2eb-136">帐户的用户名</span><span class="sxs-lookup"><span data-stu-id="8a2eb-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="8a2eb-137">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-137">string</span></span> | <span data-ttu-id="8a2eb-138">帐户的域</span><span class="sxs-lookup"><span data-stu-id="8a2eb-138">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="8a2eb-139">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-139">string</span></span> | <span data-ttu-id="8a2eb-140">帐户的用户主体名称 (UPN) </span><span class="sxs-lookup"><span data-stu-id="8a2eb-140">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="8a2eb-141">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-141">string</span></span> | <span data-ttu-id="8a2eb-142">帐户的安全标识符 (SID) </span><span class="sxs-lookup"><span data-stu-id="8a2eb-142">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="8a2eb-143">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-143">string</span></span> | <span data-ttu-id="8a2eb-144">Azure AD 中的帐户的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="8a2eb-144">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="8a2eb-145">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-145">string</span></span> | <span data-ttu-id="8a2eb-146">通讯簿中显示的帐户用户的名称。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-146">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="8a2eb-147">通常是给定的或名的名称、中间初始名称和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-147">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="8a2eb-148">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-148">string</span></span> | <span data-ttu-id="8a2eb-149">设备 (FQDN) 的完全限定的域名称</span><span class="sxs-lookup"><span data-stu-id="8a2eb-149">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="8a2eb-150">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-150">string</span></span> | <span data-ttu-id="8a2eb-151">设备类型</span><span class="sxs-lookup"><span data-stu-id="8a2eb-151">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="8a2eb-152">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-152">string</span></span> | <span data-ttu-id="8a2eb-153">计算机上运行的操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-153">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="8a2eb-154">这表示特定操作系统，包括同一系列中的变体，如 Windows 10 和 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="8a2eb-154">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="8a2eb-155">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-155">string</span></span> | <span data-ttu-id="8a2eb-156">分配给终结点的 IP 地址，并在相关的网络通信过程中使用</span><span class="sxs-lookup"><span data-stu-id="8a2eb-156">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="8a2eb-157">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-157">string</span></span> | <span data-ttu-id="8a2eb-158">运行处理录制操作的服务器应用程序的设备的名称</span><span class="sxs-lookup"><span data-stu-id="8a2eb-158">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="8a2eb-159">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-159">string</span></span> | <span data-ttu-id="8a2eb-160">运行用于处理录制操作的服务器应用程序的设备的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="8a2eb-160">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="8a2eb-161">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-161">string</span></span> | <span data-ttu-id="8a2eb-162">应用录制的操作的设备的完全限定的域名 (FQDN) </span><span class="sxs-lookup"><span data-stu-id="8a2eb-162">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="8a2eb-163">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-163">string</span></span> | <span data-ttu-id="8a2eb-164">将录制的操作应用于的帐户的显示名称</span><span class="sxs-lookup"><span data-stu-id="8a2eb-164">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="8a2eb-165">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-165">string</span></span> | <span data-ttu-id="8a2eb-166">与事件关联的城市、国家或其他地理位置</span><span class="sxs-lookup"><span data-stu-id="8a2eb-166">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="8a2eb-167">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-167">string</span></span> | <span data-ttu-id="8a2eb-168">Internet 服务提供商 (与终结点 IP 地址关联的 ISP) </span><span class="sxs-lookup"><span data-stu-id="8a2eb-168">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="8a2eb-169">long</span><span class="sxs-lookup"><span data-stu-id="8a2eb-169">long</span></span> | <span data-ttu-id="8a2eb-170">事件的唯一标识符</span><span class="sxs-lookup"><span data-stu-id="8a2eb-170">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="8a2eb-171">string</span><span class="sxs-lookup"><span data-stu-id="8a2eb-171">string</span></span> | <span data-ttu-id="8a2eb-172">有关实体或事件的其他信息</span><span class="sxs-lookup"><span data-stu-id="8a2eb-172">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8a2eb-173">相关主题</span><span class="sxs-lookup"><span data-stu-id="8a2eb-173">Related topics</span></span>
- [<span data-ttu-id="8a2eb-174">高级搜寻概述</span><span class="sxs-lookup"><span data-stu-id="8a2eb-174">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8a2eb-175">了解查询语言</span><span class="sxs-lookup"><span data-stu-id="8a2eb-175">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8a2eb-176">使用共享查询</span><span class="sxs-lookup"><span data-stu-id="8a2eb-176">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8a2eb-177">跨设备、电子邮件、应用和标识进行查寻</span><span class="sxs-lookup"><span data-stu-id="8a2eb-177">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8a2eb-178">了解架构</span><span class="sxs-lookup"><span data-stu-id="8a2eb-178">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8a2eb-179">应用查询最佳做法</span><span class="sxs-lookup"><span data-stu-id="8a2eb-179">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
