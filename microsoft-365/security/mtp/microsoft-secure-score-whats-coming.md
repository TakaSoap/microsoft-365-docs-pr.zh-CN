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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583711"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="f289d-104">Microsoft 安全分数中的情况如何？</span><span class="sxs-lookup"><span data-stu-id="f289d-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="f289d-105">为了使[Microsoft 安全得分](microsoft-secure-score.md)更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。</span><span class="sxs-lookup"><span data-stu-id="f289d-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="f289d-106">你的分数和可能的最大分数都将发生变化。</span><span class="sxs-lookup"><span data-stu-id="f289d-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="f289d-107">但是，这并不意味着您的安全状况发生了变化。</span><span class="sxs-lookup"><span data-stu-id="f289d-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="f289d-108">若要了解最近所做的更改，请参阅[Microsoft 安全分数中的新增功能？](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="f289d-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="f289d-109">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="f289d-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="f289d-110">删除不符合可靠测量预期的改进操作或不提供安全状态的有用表示形式</span><span class="sxs-lookup"><span data-stu-id="f289d-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="f289d-111">为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。</span><span class="sxs-lookup"><span data-stu-id="f289d-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="f289d-112">将 IRM 保护应用于文档</span><span class="sxs-lookup"><span data-stu-id="f289d-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="f289d-113">应用数据丢失防护策略</span><span class="sxs-lookup"><span data-stu-id="f289d-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-to-preview"></a><span data-ttu-id="f289d-114">将 Azure AD 改进操作添加到预览</span><span class="sxs-lookup"><span data-stu-id="f289d-114">Adding Azure AD improvement action to preview</span></span>

<span data-ttu-id="f289d-115">将以下 Azure Active Directory 改善操作添加到[Microsoft 安全分数的预览版本](microsoft-secure-score-preview.md)：</span><span class="sxs-lookup"><span data-stu-id="f289d-115">Adding the following Azure Active Directory improvement action to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="f289d-116">不允许用户向非托管应用程序授予许可（当前在已发布版本中可用）</span><span class="sxs-lookup"><span data-stu-id="f289d-116">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-to-preview"></a><span data-ttu-id="f289d-117">添加 Azure ATP 改进操作以供预览</span><span class="sxs-lookup"><span data-stu-id="f289d-117">Adding Azure ATP improvement actions to preview</span></span>

<span data-ttu-id="f289d-118">将以下 Azure 高级威胁防护改进操作添加到[Microsoft 安全分数的预览版本](microsoft-secure-score-preview.md)：</span><span class="sxs-lookup"><span data-stu-id="f289d-118">Adding the following Azure Advanced Threat Protection improvement actions to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="f289d-119">在域控制器上禁用打印后台处理程序服务</span><span class="sxs-lookup"><span data-stu-id="f289d-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="f289d-120">修改不安全的 Kerberos 委派以阻止模拟</span><span class="sxs-lookup"><span data-stu-id="f289d-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="f289d-121">使用 Microsoft LAPS 保护和管理本地管理员密码</span><span class="sxs-lookup"><span data-stu-id="f289d-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="f289d-122">降低横向移动路径对敏感实体的风险</span><span class="sxs-lookup"><span data-stu-id="f289d-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="f289d-123">删除敏感组中的非活动帐户</span><span class="sxs-lookup"><span data-stu-id="f289d-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="f289d-124">从实体中删除不安全的 SID 历史记录属性</span><span class="sxs-lookup"><span data-stu-id="f289d-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="f289d-125">解决不安全帐户属性</span><span class="sxs-lookup"><span data-stu-id="f289d-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="f289d-126">停止明文凭据公开</span><span class="sxs-lookup"><span data-stu-id="f289d-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="f289d-127">停止旧协议通信</span><span class="sxs-lookup"><span data-stu-id="f289d-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="f289d-128">停止弱密码使用</span><span class="sxs-lookup"><span data-stu-id="f289d-128">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a><span data-ttu-id="f289d-129">在预览中支持 Microsoft Defender ATP 威胁 & 漏洞管理（TVM）安全建议</span><span class="sxs-lookup"><span data-stu-id="f289d-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in preview</span></span>

<span data-ttu-id="f289d-130">TVM 提供的所有已发布的安全建议现在也将提供[Microsoft 安全分数的预览版本](microsoft-secure-score-preview.md)。</span><span class="sxs-lookup"><span data-stu-id="f289d-130">All released security recommendations supplied by TVM will now also be available the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md).</span></span>
