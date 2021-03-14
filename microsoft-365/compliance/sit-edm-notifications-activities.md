---
title: 创建精确数据匹配活动通知（预览）
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何为精确数据匹配活动创建通知（预览）。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a537cffe253fa20cf6838ddf3fd9a51ec440fe76
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766688"
---
# <a name="create-notifications-for-exact-data-match-activities-preview"></a><span data-ttu-id="4b1f1-103">创建精确数据匹配活动通知（预览）</span><span class="sxs-lookup"><span data-stu-id="4b1f1-103">Create notifications for exact data match activities (preview)</span></span>

<span data-ttu-id="4b1f1-104">当 [使用精确数据匹配 (EDM) 创建自定义敏感信息类型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) 时，在 [审核日志](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) 中会创建大量活动。</span><span class="sxs-lookup"><span data-stu-id="4b1f1-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span> <span data-ttu-id="4b1f1-105">可以使用 [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet 创建通知，让你了能这些活动何时开始：</span><span class="sxs-lookup"><span data-stu-id="4b1f1-105">You can use the [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="4b1f1-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="4b1f1-106">CreateSchema</span></span>
- <span data-ttu-id="4b1f1-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="4b1f1-107">EditSchema</span></span>
- <span data-ttu-id="4b1f1-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="4b1f1-108">RemoveSchema</span></span>
- <span data-ttu-id="4b1f1-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="4b1f1-109">UploadDataFailed</span></span>
- <span data-ttu-id="4b1f1-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="4b1f1-110">UploadDataCompleted</span></span>

> [!NOTE]
> <span data-ttu-id="4b1f1-111">创建 EDM 活动通知的功能仅可用于 World Wide 和 GCC 云。</span><span class="sxs-lookup"><span data-stu-id="4b1f1-111">The ability to create notifications for EDM activities is only available for the World Wide and GCC clouds only.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="4b1f1-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="4b1f1-112">Pre-requisites</span></span>

<span data-ttu-id="4b1f1-113">所使用帐户必须为下列之一：</span><span class="sxs-lookup"><span data-stu-id="4b1f1-113">The account you use must be one of the following:</span></span>

- <span data-ttu-id="4b1f1-114">全局管理员</span><span class="sxs-lookup"><span data-stu-id="4b1f1-114">a global admin</span></span>
- <span data-ttu-id="4b1f1-115">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="4b1f1-115">compliance administrator</span></span>
- <span data-ttu-id="4b1f1-116">Exchange Online 管理员</span><span class="sxs-lookup"><span data-stu-id="4b1f1-116">Exchange Online administrator</span></span>

<span data-ttu-id="4b1f1-117">若要了解有关 DLP 权限的详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="4b1f1-117">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="4b1f1-118">这些订阅中包含基于 EDM 的分类</span><span class="sxs-lookup"><span data-stu-id="4b1f1-118">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="4b1f1-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4b1f1-119">Office 365 E5</span></span>
- <span data-ttu-id="4b1f1-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4b1f1-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="4b1f1-121">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="4b1f1-121">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="4b1f1-122">Microsoft E5/A5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="4b1f1-122">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="4b1f1-123">有关 DLP 许可的详细信息，请参阅 [适用于安全与合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。</span><span class="sxs-lookup"><span data-stu-id="4b1f1-123">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="4b1f1-124">配置 EDM 活动通知</span><span class="sxs-lookup"><span data-stu-id="4b1f1-124">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="4b1f1-125">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="4b1f1-125">Connect to the [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps)</span></span> 

2. <span data-ttu-id="4b1f1-126">使用想要为其创建通知的活动运行 `New-ProtectionAlert` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b1f1-126">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="4b1f1-127">例如，如果希望在 **UploadDataCompleted** 操作发生时收到通知，请运行</span><span class="sxs-lookup"><span data-stu-id="4b1f1-127">For example, if you want to be notified when the **UploadDataCompleted** action occured, run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

<span data-ttu-id="4b1f1-128">对于 **UploadDataFailed**，可以运行</span><span class="sxs-lookup"><span data-stu-id="4b1f1-128">for the **UploadDataFailed** you can run</span></span>

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a><span data-ttu-id="4b1f1-129">相关文章</span><span class="sxs-lookup"><span data-stu-id="4b1f1-129">Related articles</span></span>

- [<span data-ttu-id="4b1f1-130">使用精确数据匹配创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="4b1f1-130">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="4b1f1-131">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="4b1f1-131">New-ProtectionAlert</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert?view=exchange-ps) 