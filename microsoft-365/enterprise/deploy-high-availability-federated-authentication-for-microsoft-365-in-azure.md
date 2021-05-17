---
title: 在 Azure 中为 Microsoft 365 部署高可用性联合身份验证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: 摘要：在 Microsoft Azure 中为 Microsoft 365 订阅配置高可用性联合Microsoft Azure。
ms.openlocfilehash: 3989ebb06b4ac5dfa1cded5e07c086c4778f94e7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919148"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a><span data-ttu-id="591e4-103">在 Azure 中为 Microsoft 365 部署高可用性联合身份验证</span><span class="sxs-lookup"><span data-stu-id="591e4-103">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>

<span data-ttu-id="591e4-104">本文包含指向使用这些虚拟机在 Azure 基础结构服务中为 Microsoft Microsoft 365 部署高可用性联合身份验证的分步说明的链接：</span><span class="sxs-lookup"><span data-stu-id="591e4-104">This article has links to the step-by-step instructions for deploying high availability federated authentication for Microsoft Microsoft 365 in Azure infrastructure services with these virtual machines:</span></span>
  
- <span data-ttu-id="591e4-105">两个 Web 应用程序代理服务器</span><span class="sxs-lookup"><span data-stu-id="591e4-105">Two web application proxy servers</span></span>
    
- <span data-ttu-id="591e4-106">两个 Active Directory 联合身份验证服务 (AD FS) 服务器</span><span class="sxs-lookup"><span data-stu-id="591e4-106">Two Active Directory Federation Services (AD FS) servers</span></span>
    
- <span data-ttu-id="591e4-107">两个副本域控制器</span><span class="sxs-lookup"><span data-stu-id="591e4-107">Two replica domain controllers</span></span>
    
- <span data-ttu-id="591e4-108">一个运行 Azure AD Connect 的目录同步服务器</span><span class="sxs-lookup"><span data-stu-id="591e4-108">One directory synchronization server running Azure AD Connect</span></span>
    
<span data-ttu-id="591e4-109">下面是包含每个服务器的占位符名称的配置。</span><span class="sxs-lookup"><span data-stu-id="591e4-109">Here is the configuration, with placeholder names for each server.</span></span>
  
<span data-ttu-id="591e4-110">**Azure 中用于 Microsoft 365 基础结构的高可用性联合身份验证**</span><span class="sxs-lookup"><span data-stu-id="591e4-110">**A high availability federated authentication for Microsoft 365 infrastructure in Azure**</span></span>

![Azure 中的高可用性和联合Microsoft 365基础结构的最终配置](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="591e4-112">所有虚拟机都位于一个跨界 Azure 虚拟网络 (VNet) 中。</span><span class="sxs-lookup"><span data-stu-id="591e4-112">All of the virtual machines are in a single cross-premises Azure virtual network (VNet).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="591e4-p101">各个用户的联合身份验证不依赖任何本地资源。不过，如果跨界连接变得不可用，VNet 中的域控制器将无法接收本地 Active Directory 域服务 (AD DS) 中执行的用户帐户和组更新。若要确保此问题不会发生，可以为跨界连接配置高可用性设置。有关详细信息，请参阅[高可用性跨界连接与 VNet 到 VNet 连接](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span><span class="sxs-lookup"><span data-stu-id="591e4-p101">Federated authentication of individual users does not rely on any on-premises resources. However, if the cross-premises connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services (AD DS). To ensure this does not happen, you can configure high availability for your cross-premises connection. For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="591e4-117">用于特定角色的每对虚拟机都位于自己的子网和可用性集中。</span><span class="sxs-lookup"><span data-stu-id="591e4-117">Each pair of virtual machines for a specific role is in its own subnet and availability set.</span></span>
  
> [!NOTE]
> <span data-ttu-id="591e4-p102">由于此 VNet 连接到本地网络，所以此配置不包括管理子网上的跳转框或监视虚拟机。有关详细信息，请参阅 [Running Windows VMs for an N-tier architecture](/azure/guidance/guidance-compute-n-tier-vm)（运行用于 N 层体系结构的 Windows VM）。</span><span class="sxs-lookup"><span data-stu-id="591e4-p102">Because this VNet is connected to the on-premises network, this configuration does not include jumpbox or monitoring virtual machines on a management subnet. For more information, see [Running Windows VMs for an N-tier architecture](/azure/guidance/guidance-compute-n-tier-vm).</span></span> 
  
<span data-ttu-id="591e4-120">此配置的结果是，您将对 Microsoft 365 所有用户进行联合身份验证，在此身份验证中，他们可以使用其 AD DS 凭据（而不是 Microsoft 365 帐户）登录。</span><span class="sxs-lookup"><span data-stu-id="591e4-120">The result of this configuration is that you will have federated authentication for all of your Microsoft 365 users, in which they can use their AD DS credentials to sign in rather than their Microsoft 365 account.</span></span> <span data-ttu-id="591e4-121">联合身份验证基础结构使用冗余的一组服务器，它们更易于在 Azure 基础结构服务（而非本地边缘网络）中进行部署。</span><span class="sxs-lookup"><span data-stu-id="591e4-121">The federated authentication infrastructure uses a redundant set of servers that are more easily deployed in Azure infrastructure services, rather than in your on-premises edge network.</span></span>
  
## <a name="bill-of-materials"></a><span data-ttu-id="591e4-122">物料清单</span><span class="sxs-lookup"><span data-stu-id="591e4-122">Bill of materials</span></span>

<span data-ttu-id="591e4-123">此基线配置需要以下 Azure 服务和组件集：</span><span class="sxs-lookup"><span data-stu-id="591e4-123">This baseline configuration requires the following set of Azure services and components:</span></span>
  
- <span data-ttu-id="591e4-124">七个虚拟机</span><span class="sxs-lookup"><span data-stu-id="591e4-124">Seven virtual machines</span></span>
    
- <span data-ttu-id="591e4-125">一个具有四个子网的跨界虚拟网络</span><span class="sxs-lookup"><span data-stu-id="591e4-125">One cross-premises virtual network with four subnets</span></span>
    
- <span data-ttu-id="591e4-126">四个资源组</span><span class="sxs-lookup"><span data-stu-id="591e4-126">Four resource groups</span></span>
    
- <span data-ttu-id="591e4-127">三个可用性集</span><span class="sxs-lookup"><span data-stu-id="591e4-127">Three availability sets</span></span>
    
- <span data-ttu-id="591e4-128">一个 Azure 订阅</span><span class="sxs-lookup"><span data-stu-id="591e4-128">One Azure subscription</span></span>
    
<span data-ttu-id="591e4-129">这里是针对此配置的虚拟机及其默认大小。</span><span class="sxs-lookup"><span data-stu-id="591e4-129">Here are the virtual machines and their default sizes for this configuration.</span></span>
  
|<span data-ttu-id="591e4-130">**项**</span><span class="sxs-lookup"><span data-stu-id="591e4-130">**Item**</span></span>|<span data-ttu-id="591e4-131">**虚拟机说明**</span><span class="sxs-lookup"><span data-stu-id="591e4-131">**Virtual machine description**</span></span>|<span data-ttu-id="591e4-132">**Azure 库图像**</span><span class="sxs-lookup"><span data-stu-id="591e4-132">**Azure gallery image**</span></span>|<span data-ttu-id="591e4-133">**默认大小**</span><span class="sxs-lookup"><span data-stu-id="591e4-133">**Default size**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="591e4-134">1.</span><span class="sxs-lookup"><span data-stu-id="591e4-134">1.</span></span>  <br/> |<span data-ttu-id="591e4-135">第一个域控制器</span><span class="sxs-lookup"><span data-stu-id="591e4-135">First domain controller</span></span>  <br/> |<span data-ttu-id="591e4-136">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="591e4-136">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="591e4-137">D2</span><span class="sxs-lookup"><span data-stu-id="591e4-137">D2</span></span>  <br/> |
|<span data-ttu-id="591e4-138">2.</span><span class="sxs-lookup"><span data-stu-id="591e4-138">2.</span></span>  <br/> |<span data-ttu-id="591e4-139">第二个域控制器</span><span class="sxs-lookup"><span data-stu-id="591e4-139">Second domain controller</span></span>  <br/> |<span data-ttu-id="591e4-140">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="591e4-140">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="591e4-141">D2</span><span class="sxs-lookup"><span data-stu-id="591e4-141">D2</span></span>  <br/> |
|<span data-ttu-id="591e4-142">3.</span><span class="sxs-lookup"><span data-stu-id="591e4-142">3.</span></span>  <br/> |<span data-ttu-id="591e4-143">Azure AD Connect 服务器</span><span class="sxs-lookup"><span data-stu-id="591e4-143">Azure AD Connect server</span></span>  <br/> |<span data-ttu-id="591e4-144">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="591e4-144">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="591e4-145">D2</span><span class="sxs-lookup"><span data-stu-id="591e4-145">D2</span></span>  <br/> |
|<span data-ttu-id="591e4-146">4.</span><span class="sxs-lookup"><span data-stu-id="591e4-146">4.</span></span>  <br/> |<span data-ttu-id="591e4-147">第一个 AD FS 服务器</span><span class="sxs-lookup"><span data-stu-id="591e4-147">First AD FS server</span></span>  <br/> |<span data-ttu-id="591e4-148">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="591e4-148">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="591e4-149">D2</span><span class="sxs-lookup"><span data-stu-id="591e4-149">D2</span></span>  <br/> |
|<span data-ttu-id="591e4-150">5.</span><span class="sxs-lookup"><span data-stu-id="591e4-150">5.</span></span>  <br/> |<span data-ttu-id="591e4-151">第二个 AD FS 服务器</span><span class="sxs-lookup"><span data-stu-id="591e4-151">Second AD FS server</span></span>  <br/> |<span data-ttu-id="591e4-152">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="591e4-152">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="591e4-153">D2</span><span class="sxs-lookup"><span data-stu-id="591e4-153">D2</span></span>  <br/> |
|<span data-ttu-id="591e4-154">6.</span><span class="sxs-lookup"><span data-stu-id="591e4-154">6.</span></span>  <br/> |<span data-ttu-id="591e4-155">第一个 Web 应用程序代理服务器</span><span class="sxs-lookup"><span data-stu-id="591e4-155">First web application proxy server</span></span>  <br/> |<span data-ttu-id="591e4-156">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="591e4-156">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="591e4-157">D2</span><span class="sxs-lookup"><span data-stu-id="591e4-157">D2</span></span>  <br/> |
|<span data-ttu-id="591e4-158">7.</span><span class="sxs-lookup"><span data-stu-id="591e4-158">7.</span></span>  <br/> |<span data-ttu-id="591e4-159">第二个 Web 应用程序代理服务器</span><span class="sxs-lookup"><span data-stu-id="591e4-159">Second web application proxy server</span></span>  <br/> |<span data-ttu-id="591e4-160">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="591e4-160">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="591e4-161">D2</span><span class="sxs-lookup"><span data-stu-id="591e4-161">D2</span></span>  <br/> |
   
<span data-ttu-id="591e4-162">若要计算此配置的估算成本，请参阅 [Azure 定价计算器](https://azure.microsoft.com/pricing/calculator/)</span><span class="sxs-lookup"><span data-stu-id="591e4-162">To compute the estimated costs for this configuration, see the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/)</span></span>
  
## <a name="phases-of-deployment"></a><span data-ttu-id="591e4-163">部署阶段</span><span class="sxs-lookup"><span data-stu-id="591e4-163">Phases of deployment</span></span>

<span data-ttu-id="591e4-164">在以下阶段部署此工作负载：</span><span class="sxs-lookup"><span data-stu-id="591e4-164">You deploy this workload in the following phases:</span></span>
  
- <span data-ttu-id="591e4-p104">[阶段 1：配置 Azure](high-availability-federated-authentication-phase-1-configure-azure.md)。创建资源组、存储帐户、可用性集和跨界虚拟网络。</span><span class="sxs-lookup"><span data-stu-id="591e4-p104">[Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md). Create resource groups, storage accounts, availability sets, and a cross-premises virtual network.</span></span>
    
- <span data-ttu-id="591e4-167">[阶段 2：配置域控制器](high-availability-federated-authentication-phase-2-configure-domain-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="591e4-167">[Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="591e4-168">创建和配置副本 AD DS 域控制器和目录同步服务器。</span><span class="sxs-lookup"><span data-stu-id="591e4-168">Create and configure replica AD DS domain controllers and the directory synchronization server.</span></span>
    
- <span data-ttu-id="591e4-p106">[阶段 3：配置 AD FS 服务器](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)。创建和配置两个 AD FS 服务器。</span><span class="sxs-lookup"><span data-stu-id="591e4-p106">[Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Create and configure the two AD FS servers.</span></span>
    
- <span data-ttu-id="591e4-p107">[阶段 4：配置 Web 应用程序代理](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)。创建和配置两个 Web 应用程序代理服务器。</span><span class="sxs-lookup"><span data-stu-id="591e4-p107">[Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). Create and configure the two web application proxy servers.</span></span>
    
- <span data-ttu-id="591e4-173">[第 5 阶段：为](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)Microsoft 365 配置联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="591e4-173">[Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="591e4-174">为订阅配置Microsoft 365身份验证。</span><span class="sxs-lookup"><span data-stu-id="591e4-174">Configure federated authentication for your Microsoft 365 subscription.</span></span>
    
<span data-ttu-id="591e4-175">这些文章提供预定义体系结构的规范性分阶段指南，以在 Azure 基础结构服务中为 Microsoft 365 创建功能、高可用性联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="591e4-175">These articles provide a prescriptive, phase-by-phase guide for a predefined architecture to create a functional, high availability federated authentication for Microsoft 365 in Azure infrastructure services.</span></span> <span data-ttu-id="591e4-176">请注意下列事项：</span><span class="sxs-lookup"><span data-stu-id="591e4-176">Keep the following in mind:</span></span>
  
- <span data-ttu-id="591e4-177">如果你是有经验的 AD FS 实施者，则可以自由调整第 3 阶段和第 4 阶段的说明，构建最符合你需求的服务器集。</span><span class="sxs-lookup"><span data-stu-id="591e4-177">If you are an experienced AD FS implementer, feel free to adapt the instructions in phases 3 and 4 and build the set of servers that best suits your needs.</span></span>
    
- <span data-ttu-id="591e4-178">如果你已经拥有现有的 Azure 混合云部署以及现有的跨界虚拟网络，则可以随意调整或跳过第 1 阶段和第 2 阶段中的说明，并将 AD FS 和 Web 应用程序代理服务器置于相应的子网上。</span><span class="sxs-lookup"><span data-stu-id="591e4-178">If you already have an existing Azure hybrid cloud deployment with an existing cross-premises virtual network, feel free to adapt or skip the instructions in phases 1 and 2 and place the AD FS and web application proxy servers on the appropriate subnets.</span></span>
    
<span data-ttu-id="591e4-179">若要构建开发/测试环境或此配置的概念证明，请参阅适用于你的开发/测试Microsoft 365[联合标识](federated-identity-for-your-microsoft-365-dev-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="591e4-179">To build a dev/test environment or a proof-of-concept of this configuration, see [Federated identity for your Microsoft 365 dev/test environment](federated-identity-for-your-microsoft-365-dev-test-environment.md).</span></span>
  
## <a name="next-step"></a><span data-ttu-id="591e4-180">后续步骤</span><span class="sxs-lookup"><span data-stu-id="591e4-180">Next step</span></span>

<span data-ttu-id="591e4-181">使用[阶段 1：配置 Azure](high-availability-federated-authentication-phase-1-configure-azure.md) 开始配置此工作负载。</span><span class="sxs-lookup"><span data-stu-id="591e4-181">Start the configuration of this workload with [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> 
