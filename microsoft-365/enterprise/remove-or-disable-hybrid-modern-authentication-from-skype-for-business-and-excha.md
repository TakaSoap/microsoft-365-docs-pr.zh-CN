---
title: 从 Skype for Business 和 Exchange 删除或禁用混合新式验证
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文介绍了如何从 Skype for Business 和 Exchange 中删除或禁用混合新式验证。
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927284"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a><span data-ttu-id="ef6e7-103">从 Skype for Business 和 Exchange 删除或禁用混合新式验证</span><span class="sxs-lookup"><span data-stu-id="ef6e7-103">Removing or disabling Hybrid Modern Authentication from Skype for Business and Exchange</span></span>

<span data-ttu-id="ef6e7-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="ef6e7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ef6e7-105">如果已启用混合新式验证 (HMA) 仅发现它不适合当前环境，可以禁用 HMA。</span><span class="sxs-lookup"><span data-stu-id="ef6e7-105">If you've enabled Hybrid Modern Authentication (HMA) only to find it's unsuitable for your current environment, you can disable HMA.</span></span> <span data-ttu-id="ef6e7-106">本文介绍如何。</span><span class="sxs-lookup"><span data-stu-id="ef6e7-106">This article explains how.</span></span>
  
## <a name="who-is-this-article-for"></a><span data-ttu-id="ef6e7-107">本文针对谁？</span><span class="sxs-lookup"><span data-stu-id="ef6e7-107">Who is this article for?</span></span>

<span data-ttu-id="ef6e7-108">如果你已启用 Skype for Business Online 或本地、和/或 Exchange Online 或本地的新式验证，并且发现你需要禁用 HMA，这些步骤适合你。</span><span class="sxs-lookup"><span data-stu-id="ef6e7-108">If you've enabled Modern Authentication in Skype for Business Online or On-premises, and/or Exchange Online or On-premises and found you need to disable HMA, these steps are for you.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef6e7-109">如果你位于 Skype for Business Online 或本地，拥有混合拓扑 HMA，并且需要在开始之前查看支持的拓扑，请参阅' Skype[for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)'一文。</span><span class="sxs-lookup"><span data-stu-id="ef6e7-109">See the '[Skype for Business topologies supported with Modern Authentication](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)' article if you're in Skype for Business Online or On-premises, have a mixed-topology HMA, and need to look at supported topologies before you begin.</span></span>
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a><span data-ttu-id="ef6e7-110">如何禁用 Exchange (混合新式) </span><span class="sxs-lookup"><span data-stu-id="ef6e7-110">How to disable Hybrid Modern Authentication (Exchange)</span></span>

1. <span data-ttu-id="ef6e7-111">**Exchange 本地**：打开 Exchange 命令行管理程序 并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ef6e7-111">**Exchange On-premises**: Open the Exchange Management Shell and run the following commands:</span></span> 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. <span data-ttu-id="ef6e7-112">**Exchange** [Online：使用远程](/powershell/exchange/connect-to-exchange-online-powershell) PowerShell 连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ef6e7-112">**Exchange Online**: [Connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) with Remote PowerShell.</span></span> <span data-ttu-id="ef6e7-113">运行以下命令以将  *OAuth2ClientProfileEnabled*  标志变成"false"：</span><span class="sxs-lookup"><span data-stu-id="ef6e7-113">Run the following command to turn your  *OAuth2ClientProfileEnabled*  flag to 'false':</span></span>

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a><span data-ttu-id="ef6e7-114">如何禁用 Skype for Business (混合新式) </span><span class="sxs-lookup"><span data-stu-id="ef6e7-114">How to disable Hybrid Modern Authentication (Skype for Business)</span></span>

1. <span data-ttu-id="ef6e7-115">**本地 Skype for Business**：在 Skype for Business 命令行管理程序 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ef6e7-115">**Skype for Business On-premises**: Run the following commands in Skype for Business Management Shell:</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. <span data-ttu-id="ef6e7-116">**Skype for Business Online：** 使用远程 PowerShell 连接到 [Skype for Business Online。](manage-skype-for-business-online-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="ef6e7-116">**Skype for Business Online**: [Connect to Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) with Remote PowerShell.</span></span> <span data-ttu-id="ef6e7-117">运行以下命令以禁用新式验证：</span><span class="sxs-lookup"><span data-stu-id="ef6e7-117">Run the following command to disable Modern Authentication:</span></span>

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

<span data-ttu-id="ef6e7-118">[链接回新式验证概述](hybrid-modern-auth-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="ef6e7-118">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) .</span></span> 
