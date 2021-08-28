---
title: 高可用性联合身份验证阶段 4 配置 Web 应用程序代理
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 1c903173-67cd-47da-86d9-d333972dda80
description: 摘要：为 web 应用程序代理服务器配置高可用性联合身份验证，Microsoft 365 Microsoft Azure。
ms.openlocfilehash: 17efeb414208afac9ce9dcb0b7136a4c962a0268
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58565216"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a>高可用性联合身份验证阶段 4：配置 Web 应用程序代理

在部署 Azure 基础结构服务中Microsoft 365身份验证的这一阶段，将创建一个内部负载平衡器以及两个 AD FS 服务器。
  
必须先完成此阶段，然后才能进入阶段[5：为](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)Microsoft 365 配置联合身份验证。 请参阅[在 Azure 中为](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)Microsoft 365部署高可用性联合身份验证了解所有阶段。
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a>在 Azure 中创建面向 Internet 的负载均衡器

必须创建面向 Internet 的负载均衡器，以便 Azure 在两个 Web 应用程序代理服务器之间平均分发来自 Internet 的传入客户端身份验证通信。
  
> [!NOTE]
> [!注意] 下面的命令集使用最新版 Azure PowerShell。 请参阅[开始Azure PowerShell。](/powershell/azure/get-started-azureps) 
  
提供位置和资源组值后，在 Azure PowerShell 命令提示符处或 PowerShell ISE 中运行生成块。
  
> [!TIP]
> 若要根据自定义设置生成可运行的 PowerShell 命令块，请使用此Microsoft Excel[工作簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)。 

```powershell
# Set up key variables
$locName="<your Azure location>"
$rgName="<Table R - Item 4 - Resource group name column>"

$publicIP=New-AzPublicIpAddress -ResourceGroupName $rgName -Name "WebProxyPublicIP" -Location $LocName -AllocationMethod "Static"
$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "WebAppProxyServers-LBFE" -PublicIpAddress $publicIP
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "WebAppProxyServers-LBBE"
$healthProbe=New-AzLoadBalancerProbeConfig -Name "WebServersProbe" -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "WebTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

若要显示分配给面向 Internet 的负载均衡器的公用 IP 地址，请在本地计算机上的 Azure PowerShell 命令提示符处运行以下命令：
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a>确定联合身份验证服务 FQDN 并创建 DNS 记录

需要确定 DNS 名称以在 Internet 上标识联合身份验证服务名称。 Azure AD 连接将在第 5 阶段Microsoft 365此名称配置 Azure AD 令牌，该名称将成为 Microsoft 365发送到连接客户端以获得安全令牌的 URL 的一部分。 例如，fs.contoso.com（fs 代表联合身份验证服务）。
  
在拥有联合身份验证服务 FDQN 之后，创建联合身份验证服务 FDQN 的公用 DNS 域 A 记录，该完全限定的域名可解析为面向 Internet 的 Azure 负载均衡器的公用 IP 地址。
  
|**名称**|**类型**|**TTL**|**值**|
|:-----|:-----|:-----|:-----|
|联合身份验证服务 FDQN  <br/> |A  <br/> |3600  <br/> |面向 Internet 的 Azure 负载均衡器的公用 IP 地址（通过上一节中的 **Write-Host** 命令显示) <br/> |
   
下面是一个示例：
  
|**名称**|**类型**|**TTL**|**值**|
|:-----|:-----|:-----|:-----|
|fs.contoso.com  <br/> |A  <br/> |3600  <br/> |131.107.249.117  <br/> |
   
接下来，将一个 DNS 地址记录添加到组织的专用 DNS 命名空间，以将联合身份验证服务 FQDN 解析为分配给 AD FS 服务器（表 I，第 4 项，值列）的内部负载均衡器的专用 IP 地址。
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a>在 Azure 中创建 Web 应用程序代理服务器虚拟机

使用下面的 Azure PowerShell 命令块为两个 Web 应用程序代理服务器创建虚拟机。  
  
请注意，以下 Azure PowerShell 命令集使用下表中的值：
  
- 表 M，用于虚拟机
    
- 表 R，用于资源组
    
- 表 V，用于虚拟网络设置
    
- 表 S，用于子网
    
- 表 I，用于静态 IP 地址
    
- 表 A（针对可用性集）
    
回想一下，你在阶段[2：](high-availability-federated-authentication-phase-2-configure-domain-controllers.md)配置域控制器中定义了表 M，在第 1 阶段：配置 Azure 中定义了表 R、V、S、I 和[A。](high-availability-federated-authentication-phase-1-configure-azure.md)
  
提供所有正确值后，在 Azure PowerShell 命令提示符处或 PowerShell ISE 上运行生成块。
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 3 - Subnet name column>"
$avName="<Table A - Item 3 - Availability set name column>"
$rgNameTier="<Table R - Item 3 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first web application proxy server virtual machine
$vmName="<Table M - Item 6 - Virtual machine name column>"
$vmSize="<Table M - Item 6 - Minimum size column>"
$staticIP="<Table I - Item 7 - Value column>"
$diskStorageType="<Table M - Item 6 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second web application proxy virtual machine
$vmName="<Table M - Item 7 - Virtual machine name column>"
$vmSize="<Table M - Item 7 - Minimum size column>"
$staticIP="<Table I - Item 8 - Value column>"
$diskStorageType="<Table M - Item 7 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> 由于这些虚拟机用于 Intranet 应用程序，所以不会为它们分配公用 IP 地址或 DNS 域名称标签，也不会将它们公开到 Internet。但是，这也意味着你无法从 Azure 门户与它们进行连接。查看虚拟机的属性时“连接”选项不可用。使用远程桌面连接附件或其他远程桌面工具连接使用其专用 IP 地址或 Intranet DNS 名称及本地 Administrator 帐户凭据的虚拟机。
  
以下是因成功完成这一阶段后生成的配置，包含占位符计算机名称。
  
**阶段 4：Azure 中用于高可用性联合身份验证基础结构的面向 Internet 的负载均衡器和 Web 应用程序代理服务器**

![第 4 阶段的高可用性Microsoft 365 Web 应用程序代理服务器部署 Azure 中的联合身份验证基础结构。](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a>后续步骤

使用[阶段 5：为](high-availability-federated-authentication-phase-5-configure-federated-authentic.md)Microsoft 365配置联合身份验证以继续配置此工作负载。
  
## <a name="see-also"></a>另请参阅

[在 Azure 中为 Microsoft 365 部署高可用性联合身份验证](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[开发/测试Microsoft 365联合标识](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365 解决方案和体系结构中心](../solutions/index.yml)