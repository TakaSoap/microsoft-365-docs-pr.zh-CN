---
title: Microsoft 安全分数中的情况如何？
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员可预期的内容。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 61f066b2fff2798e78e6379bbca46e48e93ff017
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895437"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="abc45-104">Microsoft 安全分数中的情况如何？</span><span class="sxs-lookup"><span data-stu-id="abc45-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="abc45-105">为了使 Microsoft 安全得分更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。</span><span class="sxs-lookup"><span data-stu-id="abc45-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="abc45-106">你的分数和可能的最大分数都将发生变化。</span><span class="sxs-lookup"><span data-stu-id="abc45-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="abc45-107">但是，这并不意味着您的安全状况发生了变化。</span><span class="sxs-lookup"><span data-stu-id="abc45-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="abc45-108">若要了解最近所做的更改，请参阅[Microsoft 安全分数中的新增功能？](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="abc45-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="abc45-109">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="abc45-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="abc45-110">删除不符合可靠测量预期的改进操作或不提供安全状态的有用表示形式</span><span class="sxs-lookup"><span data-stu-id="abc45-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="abc45-111">为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。</span><span class="sxs-lookup"><span data-stu-id="abc45-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="abc45-112">删除/阻止在过去30天内未使用的帐户</span><span class="sxs-lookup"><span data-stu-id="abc45-112">Delete/block accounts not used in last 30 days</span></span>
- <span data-ttu-id="abc45-113">指定少于5个全局管理员</span><span class="sxs-lookup"><span data-stu-id="abc45-113">Designate fewer than 5 global admins</span></span>
- <span data-ttu-id="abc45-114">将 IRM 保护应用于文档</span><span class="sxs-lookup"><span data-stu-id="abc45-114">Apply IRM protections to documents</span></span>
- <span data-ttu-id="abc45-115">应用数据丢失防护策略</span><span class="sxs-lookup"><span data-stu-id="abc45-115">Apply Data Loss Prevention policies</span></span>

### <a name="adding-additional-control-support-in-the-preview-version"></a><span data-ttu-id="abc45-116">在预览版本中添加其他控件支持</span><span class="sxs-lookup"><span data-stu-id="abc45-116">Adding additional control support in the preview version</span></span>
- <span data-ttu-id="abc45-117">不允许用户向非托管应用程序授予许可（当前在已发布版本中可用）</span><span class="sxs-lookup"><span data-stu-id="abc45-117">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

#### <a name="support-for-additional-microsoft-cloud-app-security-improvement-actions"></a><span data-ttu-id="abc45-118">支持其他 Microsoft 云应用安全改进操作</span><span class="sxs-lookup"><span data-stu-id="abc45-118">Support for additional Microsoft Cloud App Security improvement actions</span></span>
- <span data-ttu-id="abc45-119">在域控制器上禁用打印后台处理程序服务</span><span class="sxs-lookup"><span data-stu-id="abc45-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="abc45-120">修改不安全的 Kerberos 委派以阻止模拟</span><span class="sxs-lookup"><span data-stu-id="abc45-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="abc45-121">使用 Microsoft LAPS 保护和管理本地管理员密码</span><span class="sxs-lookup"><span data-stu-id="abc45-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="abc45-122">降低横向移动路径对敏感实体的风险</span><span class="sxs-lookup"><span data-stu-id="abc45-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="abc45-123">删除敏感组中的非活动帐户</span><span class="sxs-lookup"><span data-stu-id="abc45-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="abc45-124">从实体中删除不安全的 SID 历史记录属性</span><span class="sxs-lookup"><span data-stu-id="abc45-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="abc45-125">解决不安全帐户属性</span><span class="sxs-lookup"><span data-stu-id="abc45-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="abc45-126">停止明文凭据公开</span><span class="sxs-lookup"><span data-stu-id="abc45-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="abc45-127">停止旧协议通信</span><span class="sxs-lookup"><span data-stu-id="abc45-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="abc45-128">停止弱密码使用</span><span class="sxs-lookup"><span data-stu-id="abc45-128">Stop weak cipher usage</span></span>

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a><span data-ttu-id="abc45-129">对 Microsoft Defender ATP 威胁的支持 & 漏洞管理（TVM）安全建议</span><span class="sxs-lookup"><span data-stu-id="abc45-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations</span></span>
- <span data-ttu-id="abc45-130">TVM 提供的所有已发布的安全建议现在也将在 Microsoft 安全分数中提供。</span><span class="sxs-lookup"><span data-stu-id="abc45-130">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
