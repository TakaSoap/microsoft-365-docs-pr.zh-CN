---
title: 用于 Office Online Server 和 Office Web Apps Server 的 GDPR
description: 在本文中，你将了解如何处理 针对 Office Online Server 和 Office Web Apps Server 的 GDPR 要求。
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 84ea370f513ade134df75b2ee4e0912d6a623227
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547338"
---
# <a name="gdpr-for-office-web-apps-server-and-office-online-server"></a><span data-ttu-id="be96a-103">适用于 Office Web Apps Server 和 Office Online Server 的 GDPR</span><span class="sxs-lookup"><span data-stu-id="be96a-103">GDPR for Office Web Apps Server and Office Online Server</span></span>

<span data-ttu-id="be96a-p101">Office Online Server 和 Office Web Apps Server 遥测数据以 ULS 日志的形式存储。可以使用 [ULS 查看器](https://www.microsoft.com/download/details.aspx?id=44020)查看本地租户的 ULS 日志。</span><span class="sxs-lookup"><span data-stu-id="be96a-p101">Office Online Server and Office Web Apps Server telemetry data is stored in the form of ULS logs. You can use [ULS Viewer](https://www.microsoft.com/download/details.aspx?id=44020) to view ULS logs from your on-premises tenant.</span></span>

<span data-ttu-id="be96a-p102">每个日志行都包含一个 CorrelationID。相关的日志行使用相同的 CorrelationID。每个 CorrelationID 都与一个 SessionID 绑定，并且一个 SessionID 可能与许多 CorrelationID 相关。每个 SessionID 可能与单 个UserID 相关，但某些会话可能是匿名的，因此没有关联的 UserID。因此，为了确定哪些数据与特定用户相关联，可以从单个 UserID 映射到与该用户相关联的 SessionID，从那些 SessionID 映射到相关联的 CorrelationID，以及从 CorrelationID 映射到这些相关性中的所有日志。请参阅下图了解不同 ID 之间的关系。</span><span class="sxs-lookup"><span data-stu-id="be96a-p102">Every log line contains a CorrelationID. Related log lines share the same CorrelationID. Each CorrelationID is tied to a single SessionID, and one SessionID may be related to many CorrelationIDs. Each SessionID may be related to a single UserID, although some sessions can be anonymous and therefore not have an associated UserID. In order to determine what data is associated with a particular user, it is therefore possible to map from a single UserID to the SessionIDs associated with that user, from those SessionIDs to the associated CorrelationIDs, and from those CorrelationIDs to all the logs in those correlations. See the below diagram for the relationship between the different IDs.</span></span>

![显示 SessionIDs 和 CorrelationIds 之间关系的流程图](../media/gdpr-for-office-online-server-image1.jpg)

## <a name="gathering-logs"></a><span data-ttu-id="be96a-113">收集日志</span><span class="sxs-lookup"><span data-stu-id="be96a-113">Gathering Logs</span></span>

<span data-ttu-id="be96a-p103">例如，为了收集与 UserID 1 相关的所有日志，第一步将收集与 UserID 1 相关的所有会话（即，SessionID 1 和 SessionID 2）。下一步将收集与 SessionID 1（即，SessionID 1、2 和 3）和 SessionID 2（即，CorrelationID 4）相关的所有相关性。最后，收集与列表中每个相关性关联的所有日志。</span><span class="sxs-lookup"><span data-stu-id="be96a-p103">In order to gather all logs associated with UserID 1, for example, the first step would be to gather all sessions associated with UserID 1 (i.e. SessionID 1 and SessionID2). The next step would be to gather all correlations associated with SessionID 1 (i.e. CorrelationIDs 1, 2, and 3) and with SessionID 2 (i.e. CorrelationID 4). Finally, gather all logs associated with each of the correlations in the list.</span></span>

1. <span data-ttu-id="be96a-117">启动 UlsViewer</span><span class="sxs-lookup"><span data-stu-id="be96a-117">Launch UlsViewer</span></span>

2. <span data-ttu-id="be96a-118">打开和预期时间范围对应的 ULS 日志；ULS 日志存储在 %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS 中</span><span class="sxs-lookup"><span data-stu-id="be96a-118">Open up the uls log corresponding to the intended timeframe; ULS logs are stored in %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span></span>

3. <span data-ttu-id="be96a-119">编辑 | 修改筛选器</span><span class="sxs-lookup"><span data-stu-id="be96a-119">Edit | Modify Filter</span></span>

4. <span data-ttu-id="be96a-120">应用以下筛选器：</span><span class="sxs-lookup"><span data-stu-id="be96a-120">Apply a filter that is:</span></span>

    - <span data-ttu-id="be96a-121">EventID equals apr3y</span><span class="sxs-lookup"><span data-stu-id="be96a-121">EventID equals apr3y</span></span>

      <span data-ttu-id="be96a-122">或</span><span class="sxs-lookup"><span data-stu-id="be96a-122">Or</span></span>

    - <span data-ttu-id="be96a-123">EventID equals bp2d6</span><span class="sxs-lookup"><span data-stu-id="be96a-123">EventID equals bp2d6</span></span>

5. <span data-ttu-id="be96a-124">哈希 UserID 将位于这两个事件中任何一个的消息中</span><span class="sxs-lookup"><span data-stu-id="be96a-124">Hashed UserIds will be in the Message of either one of these two events</span></span>

6. <span data-ttu-id="be96a-125">对于 apr3y，消息将包含一个 UserID 值和一个 PUID 值</span><span class="sxs-lookup"><span data-stu-id="be96a-125">For apr3y, the Message will contain a UserID value and a PUID value</span></span>

7. <span data-ttu-id="be96a-p104">对于 bp2d6，消息将包含相当多的信息。LoggableUserId 值字段是哈希 UserID。</span><span class="sxs-lookup"><span data-stu-id="be96a-p104">For bp2d6, the Message will contain quite a bit of information. The LoggableUserId Value field is the hashed UserID.</span></span>

8. <span data-ttu-id="be96a-128">从这两个标签中任何一个获得哈希 UserID 后，ULSViewer 中该行的 WacSessionId 值将包含与该用户关联的 WacSessionId</span><span class="sxs-lookup"><span data-stu-id="be96a-128">Once the hashed UserId is obtained from either of these two tags, the WacSessionId value of that row in ULSViewer will contain the WacSessionId associated with that user</span></span>

9. <span data-ttu-id="be96a-129">收集与相关用户关联的所有 WacSessionId 值</span><span class="sxs-lookup"><span data-stu-id="be96a-129">Collect all of the WacSessionId values associated with the user in question</span></span>

10. <span data-ttu-id="be96a-130">对于列表中的第一个 WacSessionId，筛选所有等于 “xmnv” 的 EventId、等于 “UserSessionId=\<WacSessionId\> 的 Message（将筛选器的 WacSessionId\<WacSessionId\> 部分替换为 WacSessionId）</span><span class="sxs-lookup"><span data-stu-id="be96a-130">Filter for all EventId equals "xmnv", Message equals "UserSessionId=\<WacSessionId\>" for the first WacSessionId in the list (replacing the \<WacSessionId\> part of the filter with your WacSessionId)</span></span>

11. <span data-ttu-id="be96a-131">收集与该 WacSessionId 匹配的所有 Correlation 值</span><span class="sxs-lookup"><span data-stu-id="be96a-131">Collect all values of Correlation that match that WacSessionId</span></span>

12. <span data-ttu-id="be96a-132">对列表中相关用户的所有 WacSessionId 值重复步骤 10-11</span><span class="sxs-lookup"><span data-stu-id="be96a-132">Repeat steps 10-11 for all values of WacSessionId in your list for the user in question</span></span>

13. <span data-ttu-id="be96a-133">筛选列表中所有等于第一个 Correlation 的 Correlation</span><span class="sxs-lookup"><span data-stu-id="be96a-133">Filter for all Correlation equals the first Correlation in your list</span></span>

14. <span data-ttu-id="be96a-134">收集与该 Correlation 匹配的所有日志</span><span class="sxs-lookup"><span data-stu-id="be96a-134">Collect all logs matching that Correlation</span></span>

15. <span data-ttu-id="be96a-135">对列表中相关用户的所有 Correlation 值重复步骤 13-14</span><span class="sxs-lookup"><span data-stu-id="be96a-135">Repeat steps 13-14 for all values of Correlation in your list for the user in question</span></span>

## <a name="types-of-data"></a><span data-ttu-id="be96a-136">数据类型</span><span class="sxs-lookup"><span data-stu-id="be96a-136">Types of Data</span></span>

<span data-ttu-id="be96a-p105">Office 日志包含各种不同类型的数据。以下是 ULS 日志可能包含的数据示例：</span><span class="sxs-lookup"><span data-stu-id="be96a-p105">Office logs contain a variety of different types of data. The following are examples of the data that ULS logs may contain:</span></span>

- <span data-ttu-id="be96a-139">在使用产品期间遇到的问题的错误代码</span><span class="sxs-lookup"><span data-stu-id="be96a-139">Error codes for issues encountered during use of the product</span></span>

- <span data-ttu-id="be96a-140">按钮单击和其他关于应用使用情况的数据</span><span class="sxs-lookup"><span data-stu-id="be96a-140">Button clicks and other pieces of data about app usage</span></span>

- <span data-ttu-id="be96a-141">有关应用和/或应用内特定功能的性能数据</span><span class="sxs-lookup"><span data-stu-id="be96a-141">Performance data about the app and/or particular features within the app</span></span>

- <span data-ttu-id="be96a-142">有关用户计算机位置的常规位置信息（例如，来自 IP 地址的国家/地区、省/市/自治区和城市），但不是精确的地理位置。</span><span class="sxs-lookup"><span data-stu-id="be96a-142">General location information about where the user’s computer is (e.g. country / region, state, and city, derived from the IP address), but not precise geo location.</span></span>

- <span data-ttu-id="be96a-143">有关浏览器（例如浏览器名称和版本）和计算机（例如操作系统类型和版本）的基本元数据</span><span class="sxs-lookup"><span data-stu-id="be96a-143">Basic metadata about the browser, e.g. browser name and version, and the computer, e.g. OS type and version</span></span>

- <span data-ttu-id="be96a-144">来自文档主机的错误消息（例如 OneDrive、SharePoint、Exchange）</span><span class="sxs-lookup"><span data-stu-id="be96a-144">Error messages from the document host (e.g. OneDrive, SharePoint, Exchange)</span></span>

- <span data-ttu-id="be96a-145">有关应用内部进程的信息，与用户采取的任何操作无关</span><span class="sxs-lookup"><span data-stu-id="be96a-145">Information about processes internal to the app, unrelated to any action the user has taken</span></span>
