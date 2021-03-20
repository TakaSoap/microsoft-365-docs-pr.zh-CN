---
title: 使用 DAP 合作伙伴Windows PowerShell Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: 联合和云解决方案提供商 (CSP) 如何使用Windows PowerShell管理 Microsoft 365 客户租户。
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909522"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="89c8a-103">如何使用委派访问权限合作伙伴的 Windows PowerShell 管理 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89c8a-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="89c8a-104">*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*</span><span class="sxs-lookup"><span data-stu-id="89c8a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="89c8a-105">委派访问权限 (DAP) 合作伙伴是联合和云解决方案提供商 (CSP) 合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="89c8a-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="89c8a-106">许多是网络或电信提供商。</span><span class="sxs-lookup"><span data-stu-id="89c8a-106">Many are network or telecom providers.</span></span> <span data-ttu-id="89c8a-107">他们将 Microsoft 365 订阅捆绑到服务产品/服务中。</span><span class="sxs-lookup"><span data-stu-id="89c8a-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="89c8a-108">当他们销售 Microsoft 365 订阅时，他们将自动获得代表 (AOBO) 管理客户租赁的权限，以便他们可以管理和报告这些租赁。</span><span class="sxs-lookup"><span data-stu-id="89c8a-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="89c8a-109">在 Microsoft 365 管理中心中很难执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="89c8a-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="89c8a-110">使用适用于 Microsoft 365 的 PowerShell 执行管理任务要容易得多，例如：</span><span class="sxs-lookup"><span data-stu-id="89c8a-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="89c8a-111">列出所有客户 **TenantIds** 及其域</span><span class="sxs-lookup"><span data-stu-id="89c8a-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="89c8a-112">标识客户租赁中的所有用户及其分配的许可证</span><span class="sxs-lookup"><span data-stu-id="89c8a-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="89c8a-113">某些管理任务只能在 PowerShell 中完成。</span><span class="sxs-lookup"><span data-stu-id="89c8a-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="89c8a-114">以下文章介绍了联合和云解决方案提供商合作伙伴如何使用 PowerShell 管理其客户租赁：</span><span class="sxs-lookup"><span data-stu-id="89c8a-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="89c8a-115">使用 DAP Windows PowerShell委派访问权限 (Microsoft 365) 租户</span><span class="sxs-lookup"><span data-stu-id="89c8a-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="89c8a-116">使用 Windows PowerShell 为委派访问权限 (DAP) 合作伙伴将域添加到客户端租赁</span><span class="sxs-lookup"><span data-stu-id="89c8a-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="89c8a-117">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="89c8a-117">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [<span data-ttu-id="89c8a-118">通过 Windows PowerShell 为委派访问权限 (DAP) 合作伙伴检索客户报告数据</span><span class="sxs-lookup"><span data-stu-id="89c8a-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
