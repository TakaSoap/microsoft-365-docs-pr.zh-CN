---
title: 将本地网络连接到 Microsoft Azure 虚拟网络
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 81190961-5454-4a5c-8b0e-6ae75b9fb035
description: 摘要：了解如何使用站点间 VPN 连接为 Office 服务器工作负载配置跨界 Azure 虚拟网络。
ms.openlocfilehash: de8488df370b4ede9fef5ad6698d37bca6c99ac8
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58568933"
---
# <a name="connect-an-on-premises-network-to-a-microsoft-azure-virtual-network"></a>将本地网络连接到 Microsoft Azure 虚拟网络

Azure 跨界虚拟网络连接到本地网络，从而可扩展网络以包含在 Azure 基础结构服务中托管的子网和虚拟机。上述连接可让本地网络中的计算机直接访问 Azure 中的虚拟机，反之亦然。 

例如，在 Azure 虚拟机上运行的目录同步服务器需要查询本地域控制器以查询帐户更改，以及将这些更改与 Microsoft 365 订阅同步。 本文演示如何使用准备好托管 Azure 虚拟机的站点间虚拟专用网络 (VPN) 连接设置跨界 Azure 虚拟网络。

## <a name="configure-a-cross-premises-azure-virtual-network"></a>配置跨界 Azure 虚拟网络

Azure 中的虚拟机无需与本地环境隔离。若要将 Azure 虚拟机连接到本地网络资源，必须配置 Azure 跨界虚拟网络。下图显示了使用 Azure 中的虚拟机部署跨部署 Azure 虚拟网络所需的组件。
  
![通过站点到站点 VPN Microsoft Azure连接到本地网络。](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
 
在该关系图中，有两个通过站点间 VPN 连接进行连接的网络：本地网络和 Azure 虚拟网络。站点间 VPN 连接为：

- 在可寻址和位于在公共 Internet 上的两个终结点之间。
- 两端分别为本地网络中的 VPN 设备和 Azure 虚拟网络中的 Azure VPN 网关。

Azure 虚拟网络托管虚拟机。Azure 虚拟网络上从虚拟机发出的网络流量将转发到 VPN 网关，然后再跨站点间 VPN 连接将流量转发到本地网络上的 VPN 设备。本地网络的路由基础结构接着会将流量转发到其目标。

>[!Note]
>此外，你还可以使用 [ExpressRoute](https://azure.microsoft.com/services/expressroute/)，即组织和 Microsoft 网络之间的直接连接。ExpressRoute 上的流量不会在公共 Internet 上传输。本文对 ExpressRoute 的用法将不做介绍。
>
  
要设置 Azure 虚拟网络和本地网络之间的 VPN 连接，请按照以下步骤进行操作： 
  
1. 本地：为指向本地 VPN 设备的 Azure 虚拟网络的地址空间定义并创建本地网络路由。
    
2. Microsoft Azure：使用站点间 VPN 连接创建一个 Azure 虚拟网络。 
    
3. 本地：将本地硬件或软件 VPN 设备配置为终止使用遵循 Internet 协议安全性 (IPsec) 的 VPN 连接。
    
建立站点到站点 VPN 连接后，将 Azure 虚拟机添加到虚拟网络子网。
  
## <a name="plan-your-azure-virtual-network"></a>规划你的 Azure 虚拟网络
<a name="PlanningVirtual"></a>

### <a name="prerequisites"></a>先决条件
<a name="Prerequisites"></a>

- Azure 订阅。有关 Azure 订阅的信息，请转到[如何购买 Azure 页面](https://azure.microsoft.com/pricing/purchase-options/)。
    
- 可用的专用 IPv4 地址空间，将分配给虚拟网络及其子网，具有足够的空间容纳现在和将来所需的虚拟机。
    
- 本地网络中的可用 VPN 设备，用于终止支持 IPsec 要求的站点间 VPN 连接。有关详细信息，请参阅[有关用于站点间虚拟网络连接的 VPN 设备](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)。
    
- 对路由基础结构的变更，以便路由到 Azure 虚拟网络地址空间的流量转发到承载站点间 VPN 连接的 VPN 设备。
    
- Web 代理，向连接到本地网络的计算机和 Azure 虚拟网络授予 Internet 访问权限。
    
### <a name="solution-architecture-design-assumptions"></a>解决方案体系结构设计假设

下面的列表显示已为该解决方案体系结构做出的设计选择。 
  
- 此解决方案使用具有站点间 VPN 连接的单个 Azure 虚拟网络。Azure 虚拟网络承载可能包含多个虚拟机的单个子网。 
    
- 可以使用 Windows Server 2016 或 Windows Server 2012 中的路由和远程访问服务 (RRAS) 在本地网络和 Azure 虚拟网络之间建立 IPsec 站点间 VPN 连接。还可以使用其他选项，例如 Cisco 或 Juniper Networks VPN 设备。
    
- 本地网络可能还具有 Active Directory 域服务 (AD DS)、域名系统 (DNS) 和代理服务器等网络资源。根据你的要求，它可能在将部分网络资源放到 Azure 虚拟网络中时非常有帮助。
    
对于具有一个或多个子网的现有 Azure 虚拟网络，确定是否还有剩余的地址空间以便附加子网托管您所需的虚拟机，具体取决于您的要求。如果您没有供附加子网使用的剩余地址空间，请创建具有站点间 VPN 连接的其他虚拟网络。
  
### <a name="plan-the-routing-infrastructure-changes-for-the-azure-virtual-network"></a>规划 Azure 虚拟网络的路由基础结构变更

您必须将本地路由基础结构配置为将目标为 Azure 虚拟网络的地址空间的流量转发到承载站点间 VPN 连接的本地 VPN 设备。
  
更新路由基础结构的具体方法取决于您管理路由信息的方式，可能的选项如下：
  
- 基于手动配置路由表更新。
    
- 基于路由协议路由表更新，例如路由信息协议 (RIP) 或开放式最短路径优先 (OSPF) 协议。
    
咨询路由专家，确保目标为 Azure 虚拟网络的流量将转发到本地 VPN 设备。
  
### <a name="plan-for-firewall-rules-for-traffic-to-and-from-the-on-premises-vpn-device"></a>规划发送到本地 VPN 设备以及从本地 VPN 设备发出的流量的防火墙规则

如果您的 VPN 位于一个外围网络，且该外围网络和 Internet 之间存在防火墙，您可能需要对防火墙进行配置，以便以下规则允许站点间 VPN 连接。
  
- 到 VPN 设备的流量（从 Internet 传入）：
    
  - VPN 设备的目标 IP 地址和 IP 协议 50
    
  - VPN 设备的目标 IP 地址和 UDP 目标端口 500
    
  - VPN 设备的目标 IP 地址和 UDP 目标端口 4500
    
- 来自 VPN 设备的流量（传出到 Internet）：
    
  - VPN 设备的源 IP 地址和 IP 协议 50
    
  - VPN 设备的源 IP 地址和 UDP 源端口 500
    
  - VPN 设备的源 IP 地址和 UDP 源端口 4500
    
### <a name="plan-for-the-private-ip-address-space-of-the-azure-virtual-network"></a>规划 Azure 虚拟网络的专用 IP 地址空间

Azure 虚拟网络的专用 IP 地址空间必须能够容纳 Azure 用于承载虚拟网络的地址，且具有至少一个有足够地址供 Azure 虚拟机使用的子网。
  
要确定子网需要的地址数量，请计算您现在需要的虚拟机数量，估计未来增长的数量，然后使用下表确定子网大小。
  
|**所需的虚拟机数量**|**所需的主机位数**|**子网大小**|
|:-----|:-----|:-----|
|1-3  <br/> |3   <br/> |/29  <br/> |
|4-11  <br/> |4   <br/> |/28  <br/> |
|12-27  <br/> |5   <br/> |/27  <br/> |
|28-59  <br/> |6   <br/> |/26  <br/> |
|60-123  <br/> |7   <br/> |/25  <br/> |
   
### <a name="planning-worksheet-for-configuring-your-azure-virtual-network"></a>用于配置 Azure 虚拟网络的规划工作表
<a name="worksheet"> </a>

在创建托管虚拟机的 Azure 虚拟网络之前，您必须在下表中确定所需的设置。
  
有关虚拟网络的设置，请填写表 V。
  
 **表 V：跨部署虚拟网络配置**
  
|**项**|**Configuration 元素**|**说明**|**值**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |虚拟网络名称  <br/> |要分配给 Azure 虚拟网络的名称（例如，DirSyncNet）。  <br/> |![行。](../media/Common-Images/TableLine.png) |
|2.  <br/> |虚拟网络位置  <br/> |将包含虚拟网络的 Azure 数据中心（如美国西部）。  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |VPN 设备 IP 地址  <br/> |Internet 上 VPN 设备接口的公用 IPv4 地址。与 IT 部门协作，以确定该地址。  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |虚拟网络地址空间  <br/> |虚拟网络地址空间（在一组专用地址前缀中定义）。与 IT 部门协作，以确定该地址空间。地址空间应为无类别域际路由选择 (CIDR) 格式，也称为网络前缀格式。例如，10.24.64.0/20。  <br/> |![行。](../media/Common-Images/TableLine.png) <br/> |
|5.  <br/> |IPsec 共享的密钥  <br/> |一组 32 位字符的随机字母数字字符串，用于对站点间 VPN 连接的两端进行身份验证。与 IT 或安全部门协作来确定此密钥值，然后将其存储在安全的位置。或者，请参阅[创建 IPsec 预共享密钥的随机字符串](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx)。<br/> |![行。](../media/Common-Images/TableLine.png) <br/> |
   
此解决方案的子网请填写表 S。
  
- 对于第一个子网，请为 Azure 网关子网确定 28 位的地址空间（带有 /28 前缀长度）。有关如何确定此地址空间的信息，请参阅 [Calculating the gateway subnet address space for Azure virtual networks](/archive/blogs/solutions_advisory_board/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks)（计算 Azure 虚拟网络的网关子网地址空间）。
    
- 对于第二个子网，请指定友好名称（基于虚拟网络地址空间的单一 IP 地址空间）和描述性目的。
    
与 IT 部门协作以确定这些虚拟网络地址空间中的地址空间。这两个地址空间应为 CIDR 格式。
  
 **表 S：虚拟网络中的子网**
  
|**项**|**子网名称**|**子网地址空间**|**用途**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |GatewaySubnet  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |Azure 网关使用的子网。  <br/> |
|2.  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |
   
对于您想要让虚拟网络中的虚拟机使用的本地 DNS 服务器，请填写表 D。为 DNS 服务器提供友好名称和单一 IP 地址。此友好名称不需要与 DNS 服务器的主机名或计算机名相匹配。请注意已列出两个空白条目，但您可以添加更多。与 IT 部门协作，以确定该列表。
  
 **表 D：本地 DNS 服务器**
  
|**项**|**DNS 服务器的友好名称**|**DNS 服务器的 IP 地址**|
|:-----|:-----|:-----|
|1.  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |
   
要通过站点间 VPN 连接将数据包从 Azure 虚拟网络传输到组织网络，则必须使用本地网络配置虚拟网络。此本地网络包含组织的本地网络上的所有位置的地址空间列表（使用 CIDR 格式），虚拟网络中的虚拟机必须能够访问这些本地网络。这可能是本地网络上的所有位置或部分位置。用于定义本地网络的地址空间列表必须是唯一的，并且不得与用于此虚拟网络或其他跨界虚拟网络的地址空间重叠。
  
对于本地网络地址空间集，请填写表 L。请注意已列出三个空白条目，但通常需要更多。与 IT 部门协作，以确定该列表。
  
 **表 L：本地网络的地址前缀**
  
|**项**|**本地网络地址空间**|
|:-----|:-----|
|1.  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![行。](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |![线条](../media/Common-Images/TableLine.png)  <br/> |
   
## <a name="deployment-roadmap"></a>部署路线图
<a name="DeploymentRoadmap"> </a>

在 Azure 中创建跨界虚拟网络并添加虚拟机包含三个阶段：
  
- 阶段 1：准备本地网络。
    
- 阶段 2：在 Azure 中创建跨界虚拟网络。
    
- 阶段 3（可选）：添加虚拟机。
    
### <a name="phase-1-prepare-your-on-premises-network"></a>阶段 1：准备您的本地网络:
<a name="Phase1"></a>

必须配置本地网络，其中路由指向目标为虚拟网络地址空间的流量并将流量提供给本地网络边缘中的路由器。请咨询你的网络管理员，以确定如何将路由添加到本地网络的路由结构。
  
下面是生成的配置。
  
![本地网络上必须有指向 VPN 设备的虚拟网络地址空间的路由。](../media/90bab36b-cb60-4ea5-81d5-4737b696d41c.png)
  
### <a name="phase-2-create-the-cross-premises-virtual-network-in-azure"></a>阶段 2：在 Azure 中创建跨部署虚拟网络
<a name="Phase2"></a>

首先，请打开 Azure PowerShell 提示符。如果没有安装 Azure PowerShell，请参阅 [Azure PowerShell 使用入门](/powershell/azure/get-started-azureps)。

 
下一步，使用此命令登录 Azure 帐户。
  
```powershell
Connect-AzAccount
```

使用以下命令获得订阅名称。
  
```powershell
Get-AzSubscription | Sort SubscriptionName | Select SubscriptionName
```

通过这些命令设置 Azure 订阅。使用正确的订阅名称替换引号内的所有内容（包括 < 和 > 字符）。
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

接下来，为虚拟网络创建一个新的资源组。要确定一个唯一的资源组名称，请使用此命令列出您现有的资源组。
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

使用这些命令创建新的资源组。
  
```powershell
$rgName="<resource group name>"
$locName="<Table V - Item 2 - Value column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

接下来，请创建 Azure 虚拟网络。
  
```powershell
# Fill in the variables from previous values and from Tables V, S, and D
$rgName="<name of your new resource group>"
$locName="<Azure location of your new resource group>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$gwSubnetPrefix="<Table S - Item 1 - Subnet address space column>"
$SubnetName="<Table S - Item 2 - Subnet name column>"
$SubnetPrefix="<Table S - Item 2 - Subnet address space column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the Azure virtual network and a network security group that allows incoming remote desktop connections to the subnet that is hosting virtual machines
$gatewaySubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnetPrefix
$vmSubnet=New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $SubnetPrefix
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gatewaySubnet,$vmSubnet -DNSServer $dnsServers
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName -Location $locShortName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$nsg=Get-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $SubnetName -AddressPrefix $SubnetPrefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

下面是生成的配置。
  
![虚拟网络尚未连接到本地网络。](../media/54a37782-a6cc-4d48-b38d-73e128b44a82.png)
  
下一步，请使用这些命令来创建站点间 VPN 连接的网关。
  
```powershell
# Fill in the variables from previous values and from Tables V and L
$vnetName="<Table V - Item 1 - Value column>"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -SubnetId $vnet.Subnets[0].Id
# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig
# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix
# Create the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway
```

下面是生成的配置。
  
![虚拟网络现有一个网关。](../media/82dd66b2-a4b7-48f6-a89b-cfdd94630980.png)
  
接下来，请将本地 VPN 设备配置为连接到 Azure VPN 网关。有关详细信息，请参阅[有关用于站点间 Azure 虚拟网络连接的 VPN 设备](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)。
  
若要配置 VPN 设备，您需要以下各项:
  
- 用于虚拟网络的 Azure VPN 网关的公用 IPv4 地址。 使用 **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** 命令显示此地址。
    
- 站点间 VPN 连接的 IPsec 预共享密钥（表 V - 项 5 - 值列）
    
下面是生成的配置。
  
![虚拟网络现已连接到本地网络。](../media/6379c423-4f22-4453-941b-7ff32484a0a5.png)
  
### <a name="phase-3-optional-add-virtual-machines"></a>阶段 3（可选）：添加虚拟机

在 Azure 中创建所需的虚拟机。有关详细信息，请参阅[在 Azure 门户中创建 Windows 虚拟机](https://go.microsoft.com/fwlink/p/?LinkId=393098)。
  
使用以下设置：
  
- 在“基本信息”选项卡中，选择与虚拟网络相同的订阅和资源组。稍后将需要使用这些信息登录到虚拟机。在“实例详细信息”部分中，选择适当的虚拟机大小。在安全位置记录管理员帐户用户名和密码。 
    
- 在“网络”选项卡中，选择虚拟网络的名称和托管虚拟机（非网关子网）的子网。将所有其他设置保留为其默认值。
    
请检查内部 DNS 验证虚拟机是否正确使用 DNS，确保已为新虚拟机添加地址 (A) 记录。要访问 Internet，必须将 Azure 虚拟机配置为使用本地网络的代理服务器。有关要在服务器上执行的其他配置步骤，请与网络管理员联系。
  
下面是生成的配置。
  
![虚拟网络现在托管可从本地网络访问的虚拟机。](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
  
## <a name="next-step"></a>后续步骤
  
[在Microsoft 365部署目录Microsoft Azure](deploy-microsoft-365-directory-synchronization-dirsync-in-microsoft-azure.md)