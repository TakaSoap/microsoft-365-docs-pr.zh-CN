---
title: Microsoft 365客户端应用支持：条件访问
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: 本文将了解哪些平台、客户端和 PowerShell 模块支持条件Microsoft 365 专属 Access。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 763380429b8643c5dd01971117fccb040a9a0210
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286557"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="c24d3-103">Microsoft 365客户端应用支持：条件访问</span><span class="sxs-lookup"><span data-stu-id="c24d3-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="c24d3-104">在现代工作场所中，用户可以从任何位置使用各种设备和应用访问组织的资源。</span><span class="sxs-lookup"><span data-stu-id="c24d3-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="c24d3-105">因此，只关注谁可以访问资源已不够用。</span><span class="sxs-lookup"><span data-stu-id="c24d3-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="c24d3-106">您的组织还必须支持在访问控制基础结构中访问资源以及如何访问资源。</span><span class="sxs-lookup"><span data-stu-id="c24d3-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="c24d3-107">使用Azure Active Directory、位置和基于多重身份验证的条件访问，你可以满足此新要求。</span><span class="sxs-lookup"><span data-stu-id="c24d3-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="c24d3-108">条件访问是一项Azure Active Directory，它使你能够强制执行对环境中应用的访问权限控制，所有这些操作都基于特定条件，并且从一个中心位置进行管理。</span><span class="sxs-lookup"><span data-stu-id="c24d3-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="c24d3-109">详细了解条件Azure Active Directory[访问](/azure/active-directory/conditional-access/)。</span><span class="sxs-lookup"><span data-stu-id="c24d3-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="c24d3-110">受支持的客户端&平台</span><span class="sxs-lookup"><span data-stu-id="c24d3-110">Supported clients & platforms</span></span>

<span data-ttu-id="c24d3-111">以下客户端和平台的最新版本支持条件访问。</span><span class="sxs-lookup"><span data-stu-id="c24d3-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="c24d3-112">有关应用程序平台支持Microsoft 365，请参阅 system [requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)。</span><span class="sxs-lookup"><span data-stu-id="c24d3-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="c24d3-113">支持的 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="c24d3-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="c24d3-114">Azure Active DirectoryPowerShell</span><span class="sxs-lookup"><span data-stu-id="c24d3-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="c24d3-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="c24d3-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="c24d3-116">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="c24d3-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
