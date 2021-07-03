---
title: Microsoft 365客户端应用支持：多重身份验证
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 本文将了解哪些平台、客户端和 PowerShell 模块支持对 Microsoft 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8749c05e3f7ce5dacf7d3ed1eaa46a46a20482d5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286449"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="2e1ef-103">Microsoft 365客户端应用支持：多重身份验证</span><span class="sxs-lookup"><span data-stu-id="2e1ef-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="2e1ef-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="2e1ef-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2e1ef-105">为了提供登录的额外安全级别，客户端可以配置为使用多重身份验证 (MFA) ，它使用用户密码和基于：</span><span class="sxs-lookup"><span data-stu-id="2e1ef-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="2e1ef-106">其拥有中无法轻松复制的一些内容，例如智能手机。</span><span class="sxs-lookup"><span data-stu-id="2e1ef-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="2e1ef-107">用户具有唯一且唯一的一些内容，例如其指纹、面部或其他生物识别属性</span><span class="sxs-lookup"><span data-stu-id="2e1ef-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="2e1ef-108">了解有关多重 [身份验证的更多信息](/azure/active-directory/authentication/multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="2e1ef-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="2e1ef-109">受支持的客户端&平台</span><span class="sxs-lookup"><span data-stu-id="2e1ef-109">Supported clients & platforms</span></span>

<span data-ttu-id="2e1ef-110">以下客户端和平台的最新版本支持多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="2e1ef-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="2e1ef-111">有关应用程序平台支持Microsoft 365，请参阅 system [requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)。</span><span class="sxs-lookup"><span data-stu-id="2e1ef-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="2e1ef-112">支持的 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="2e1ef-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="2e1ef-113">Azure Active DirectoryPowerShell</span><span class="sxs-lookup"><span data-stu-id="2e1ef-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="2e1ef-114">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e1ef-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="2e1ef-115">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e1ef-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
