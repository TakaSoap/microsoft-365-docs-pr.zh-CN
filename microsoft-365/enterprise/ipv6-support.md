---
title: Office 365 服务中的 IPv6 支持
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 摘要：介绍了在 Microsoft Office 365 组件和 Office 365 政府产品/服务中的 IPv6 支持。
ms.openlocfilehash: a509b19711092bddf153a677c41860e7a4e5277a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028903"
---
# <a name="ipv6-support-in-office-365-services"></a><span data-ttu-id="a7ed1-103">Office 365 服务中的 IPv6 支持</span><span class="sxs-lookup"><span data-stu-id="a7ed1-103">IPv6 support in Office 365 services</span></span>

<span data-ttu-id="a7ed1-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="a7ed1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a7ed1-105">Office 365 支持 IPv6 和 IPv4;但是，并非所有 Office 365 功能都使用 IPv6 完全启用。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-105">Office 365 supports both IPv6 and IPv4; however, not all Office 365 features are fully enabled with IPv6.</span></span> <span data-ttu-id="a7ed1-106">这意味着您必须同时使用 IPv4 和 IPv6 连接到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-106">This means that you must use both IPv4 and IPv6 to connect to Office 365.</span></span> <span data-ttu-id="a7ed1-107">如果要筛选到 Office 365 的出站流量，可在文章 [Office 365 URL 和 IP](urls-and-ip-address-ranges.md)地址范围 中查看 Office 365 支持的 IPv6 地址的完整列表。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-107">If you are filtering your outbound traffic to Office 365, the full list of IPv6 addresses that are supported by Office 365 can be found in the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span> <span data-ttu-id="a7ed1-108">配置网络并允许相应的 IPv6 地址后，可以从 Microsoft 下载中心下载 [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) 测试计划。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-108">After your network is configured and the appropriate IPv6 addresses are allowed, you can download the [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) from the Microsoft Download Center.</span></span>
  
## <a name="ipv6-support-in-office-365-subscription-service"></a><span data-ttu-id="a7ed1-109">Office 365 订阅服务中的 IPv6 支持</span><span class="sxs-lookup"><span data-stu-id="a7ed1-109">IPv6 support in Office 365 subscription service</span></span>

### <a name="exchange-online-and-ipv6"></a><span data-ttu-id="a7ed1-110">Exchange Online 和 IPv6</span><span class="sxs-lookup"><span data-stu-id="a7ed1-110">Exchange Online and IPv6</span></span>

<span data-ttu-id="a7ed1-111">如果用于连接到 Exchange Online 的程序支持 IPv6，它将默认在有线和无线网络上使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-111">If the program that you use to connect to Exchange Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="a7ed1-112">如果要控制与 Exchange Online 的通信，请使用 [Office 365 URL](urls-and-ip-address-ranges.md)中的 IP 地址范围和 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-112">If you want to control communications to Exchange Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="sharepoint-online-and-ipv6"></a><span data-ttu-id="a7ed1-113">SharePoint Online 和 IPv6</span><span class="sxs-lookup"><span data-stu-id="a7ed1-113">SharePoint Online and IPv6</span></span>

 <span data-ttu-id="a7ed1-114">**Office 365 政府版 G1/G3/G4/K1** 如果用于连接到 SharePoint Online 的程序支持 IPv6，它将默认尝试使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-114">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
 <span data-ttu-id="a7ed1-115">**公共多租户云** Microsoft 将应你的请求启用 SharePoint Online IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-115">**Public multi-tenant cloud** Microsoft enables SharePoint Online IPv6 at your request.</span></span> <span data-ttu-id="a7ed1-116">您需要为组织的 DNS 基础结构提供 CIDR 表示 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-116">You need to provide the CIDR notated IP addresses for your organization's DNS infrastructure.</span></span> <span data-ttu-id="a7ed1-117">请记住，其他组织无法共享此 DNS 基础结构，无法为租户启用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-117">Keep in mind that this DNS infrastructure can't be shared by other organizations for IPv6 to be enabled for your tenant.</span></span> <span data-ttu-id="a7ed1-118">启用 IPv6 后，如果用于连接到 SharePoint Online 的程序支持 IPv6，它将默认使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-118">After IPv6 is enabled, if the program that you use to connect to SharePoint Online supports IPv6, it uses IPv6 by default.</span></span>
  
<span data-ttu-id="a7ed1-119">如果用于连接到 SharePoint Online 的程序支持 IPv6，它将默认在有线和无线网络上使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-119">If the program that you use to connect to SharePoint Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="a7ed1-120">如果要控制与 SharePoint Online 的通信，请使用 [Office 365 URL](urls-and-ip-address-ranges.md)中的 IP 地址范围和 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-120">If you want to control communications to SharePoint Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
 
  
### <a name="skype-for-business-and-ipv6"></a><span data-ttu-id="a7ed1-121">Skype for Business 和 IPv6</span><span class="sxs-lookup"><span data-stu-id="a7ed1-121">Skype for Business and IPv6</span></span>

<span data-ttu-id="a7ed1-122">请注意，IPv6 在 Skype for Business 中不受支持，不能再启用。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-122">Please be aware IPv6 is not supported in Skype for Business and can no longer be enabled.</span></span>

### <a name="microsoft-teams-and-ipv6"></a><span data-ttu-id="a7ed1-123">Microsoft Teams 和 IPV6</span><span class="sxs-lookup"><span data-stu-id="a7ed1-123">Microsoft Teams and IPV6</span></span>

<span data-ttu-id="a7ed1-124">Microsoft Teams 直接路由仅支持 IPv4。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-124">Microsoft Teams Direct Routing only supports IPv4.</span></span> <span data-ttu-id="a7ed1-125">Microsoft Teams 服务和客户端同时支持 IPv4 和 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-125">The Microsoft Teams service and client support both IPv4 and IPv6.</span></span> <span data-ttu-id="a7ed1-126">如果要控制与 Microsoft Teams 的通信，请使用 [Office 365 URL](urls-and-ip-address-ranges.md)中的 IP 地址范围和 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-126">If you want to control communications to Microsoft Teams, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="exchange-online-protection-and-ipv6"></a><span data-ttu-id="a7ed1-127">Exchange Online Protection 和 IPv6</span><span class="sxs-lookup"><span data-stu-id="a7ed1-127">Exchange Online Protection and IPv6</span></span>

<span data-ttu-id="a7ed1-128">Exchange Online Protection (EOP) 传输通过传输层安全性协议进行时支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-128">Exchange Online Protection (EOP) supports IPv6 if the transmission occurs over Transport Layer Security Protocol.</span></span> <span data-ttu-id="a7ed1-129">对于 EOP 范围，请使用 [Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-129">For the EOP range, use [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="ipv6-support-for-office-365-government-offerings"></a><span data-ttu-id="a7ed1-130">Office 365 政府版产品/服务 IPv6 支持</span><span class="sxs-lookup"><span data-stu-id="a7ed1-130">IPv6 support for Office 365 government offerings</span></span>

<span data-ttu-id="a7ed1-131">针对政府产品/服务 Office 365 IPv6 的支持符合管理和预算办公室 (OMB) （针对管理层和机构的首席信息官）以及美国政府采用 Internet 协议版本 6 (IPv6) 的规定。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-131">Office 365 IPv6 support for government offerings conforms to the Office of Management and Budget (OMB) Memorandum for Chief Information Officers of Executive Departments and Agencies, as well as the Federal Government Adoption of Internet Protocol Version 6 (IPv6) memorandum.</span></span> <span data-ttu-id="a7ed1-132">[Microsoft Office 365 政府](https://go.microsoft.com/fwlink/p/?LinkId=325414) 版是一种多租户服务，可将美国政府数据存储在隔离社区云中。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-132">[Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) is a multi-tenant service that stores US government data in a segregated community cloud.</span></span> <span data-ttu-id="a7ed1-133">与其他 Office 365 产品/服务一样，它提供生产力和协作服务，包括 Exchange Online、Skype for Business、SharePoint Online 和 Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-133">Like other Office 365 offerings, it provides productivity and collaboration services, including Exchange Online, Skype for Business, SharePoint Online, and Microsoft 365 Apps for enterprise.</span></span> 

<span data-ttu-id="a7ed1-134">365 Microsoft Office 365 政府版产品/服务仅适用于 2013 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-134">The Microsoft Office 365 government offerings apply only for 2013 and later.</span></span> <span data-ttu-id="a7ed1-135">有关 Office 365 政府版产品/服务详细信息，请参阅 [宣布推出 Office 365 政府版：美国政府社区云](https://go.microsoft.com/fwlink/p/?LinkId=325414)。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-135">For more information about the Office 365 government offerings, see [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414).</span></span> <span data-ttu-id="a7ed1-136">《国际武器贸易条例》 (ITAR) 是一组美国政府法规，可控制美国《美国国防》列表 (USML) 上的与防御相关的文章和服务的导出 [和导入 ](https://go.microsoft.com/fwlink/p/?LinkId=325415)。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-136">International Traffic in Arms Regulations (ITAR) is a set of US government regulations that control the export and import of defense-related articles and services on the [United States Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415).</span></span> 

<span data-ttu-id="a7ed1-137">Microsoft Office 365 企业版为 Microsoft 生产力解决方案提供专用托管服务，以支持要求联邦信息安全管理 (FISMA) 认证的美国联邦机构的安全、隐私和法规遵从性要求以及受 ITAR 限制的商业实体。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-137">Microsoft Office 365 for Enterprises provides dedicated hosting services for Microsoft productivity solutions that support the security, privacy, and regulatory compliance requirements for US federal agencies requiring Federal Information Security Management (FISMA) certification and commercial entities subject to ITAR.</span></span>
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a><span data-ttu-id="a7ed1-138">使用 IPv6 和 Office 365 时要考虑的问题</span><span class="sxs-lookup"><span data-stu-id="a7ed1-138">Things to consider when using IPv6 and Office 365</span></span>

<span data-ttu-id="a7ed1-139">建议您不要禁用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-139">We recommend that you do not disable IPv6.</span></span> <span data-ttu-id="a7ed1-140">有关详细信息，请参阅本指南 [文章](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-140">For more information, see this [guidance article](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span></span> <span data-ttu-id="a7ed1-141">若要确定网络上使用哪些 IP 版本，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="a7ed1-141">To determine what IP versions are being used on your network, consider the following:</span></span>
  
- <span data-ttu-id="a7ed1-142">如果在命令提示符下显示 **IPConfig** 命令包含名为"IPv6 地址"或"临时 IPv6 地址"的行，则环境中有 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-142">If the display of the **IPConfig** command at the command prompt contains rows named "IPv6 Address" or "Temporary IPv6 Address," you have IPv6 in your environment.</span></span>

- <span data-ttu-id="a7ed1-143">如果所有 IPv6 地址均以"fe80"开头，并且对应于名为"Link-Local IPv6 Address"的行，则环境中没有 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-143">If all the IPv6 addresses begin with "fe80" and correspond to rows named "Link-Local IPv6 Address," you don't have IPv6 in your environment.</span></span>

<span data-ttu-id="a7ed1-144">这些注意事项可能适用于你的网络：</span><span class="sxs-lookup"><span data-stu-id="a7ed1-144">These considerations might apply to your network:</span></span>
  
- <span data-ttu-id="a7ed1-145">公共订阅服务不支持通过 IPv6 通过信用卡购买。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-145">The public subscription service does not support purchase by credit card over IPv6.</span></span> <span data-ttu-id="a7ed1-146">这不适用于政府社区云 (GCC) ，因为政府企业协议 (EA) 许可。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-146">This does not apply to the Government Community Cloud (GCC) because governments have Enterprise Agreement (EA) licensing.</span></span>

- <span data-ttu-id="a7ed1-147">IPv6 不支持某些权限管理服务 (RMS) 方案。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-147">IPv6 does not support some Rights Management Services (RMS) scenarios.</span></span>

- <span data-ttu-id="a7ed1-148">IPv6 不支持 BlackBerry® ENTERPRISE Server (BES) 因为 BlackBerry 不支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-148">IPv6 does not support BlackBerry® Enterprise Server (BES) because BlackBerry doesn't support IPv6.</span></span>

- <span data-ttu-id="a7ed1-149">如果将 Active Directory 联合身份验证服务 (AD FS) Office 365，则不支持使用 IPv6 向 Office 365 发布 AD FS 网络终结点。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-149">If you use Active Directory Federation Services (AD FS) with Office 365, advertising your AD FS network endpoint to Office 365 using IPv6 is not supported.</span></span> <span data-ttu-id="a7ed1-150">使用 Exchange Online 时，AD FS DNS 条目中不应包含 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="a7ed1-150">You should not include AAAA records in the AD FS DNS entry when using Exchange Online.</span></span> 

<span data-ttu-id="a7ed1-151">以下是可以用于返回的简短链接：[https://aka.ms/o365ip6]()</span><span class="sxs-lookup"><span data-stu-id="a7ed1-151">Here's a short link you can use to come back: [https://aka.ms/o365ip6]()</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7ed1-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7ed1-152">See also</span></span>

<span data-ttu-id="a7ed1-153">[IPv6 学习路线图](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span><span class="sxs-lookup"><span data-stu-id="a7ed1-153">[IPv6 Learning Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span></span>
  
[<span data-ttu-id="a7ed1-154">IPv6 生存指南</span><span class="sxs-lookup"><span data-stu-id="a7ed1-154">IPv6 Survival Guide</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
