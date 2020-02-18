---
title: Microsoft 365 测试环境中的模拟跨界虚拟网络
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
description: 摘要：在 Microsoft Azure 中创建模拟跨界虚拟网络作为 Microsoft 365 测试环境。
ms.openlocfilehash: 52ba80d8613f44b252389da87891359eadae752a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084155"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a><span data-ttu-id="7b0b6-103">Microsoft 365 测试环境中的模拟跨界虚拟网络</span><span class="sxs-lookup"><span data-stu-id="7b0b6-103">Simulated cross-premises virtual network in a Microsoft 365 test environment</span></span>

<span data-ttu-id="7b0b6-104">*本测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="7b0b6-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="7b0b6-p101">本文逐步介绍了如何使用两个 Azure 虚拟网络来创建 Microsoft Azure 模拟混合云环境。下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-p101">This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks. Here is the resulting configuration.</span></span> 
  
![第 3 阶段的模拟跨界虚拟网络测试环境，XPrem VNet 中有 DC2 虚拟机](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="7b0b6-108">此配置模拟 Azure IaaS 混合云生产环境，具体包括：</span><span class="sxs-lookup"><span data-stu-id="7b0b6-108">This simulates an Azure IaaS hybrid cloud production environment and consists of:</span></span>
  
- <span data-ttu-id="7b0b6-109">Azure 虚拟网络中托管的模拟简化本地网络（TestLab 虚拟网络）。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-109">A simulated and simplified on-premises network hosted in an Azure virtual network (the TestLab virtual network).</span></span>
    
- <span data-ttu-id="7b0b6-110">Azure 中托管的模拟跨界虚拟网络 (XPrem)。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-110">A simulated cross-premises virtual network hosted in Azure (XPrem).</span></span>
    
- <span data-ttu-id="7b0b6-111">两个虚拟网络之间的 VNet 对等关系。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-111">A VNet peering relationship between the two virtual networks.</span></span>
    
- <span data-ttu-id="7b0b6-112">XPrem 虚拟网络中辅助域控制器。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-112">A secondary domain controller in the XPrem virtual network.</span></span>
    
<span data-ttu-id="7b0b6-113">这是你执行以下操作的常见基础入手配置：</span><span class="sxs-lookup"><span data-stu-id="7b0b6-113">This provides a basis and common starting point from which you can:</span></span> 
  
- <span data-ttu-id="7b0b6-114">在模拟 Azure IaaS 混合云环境中开发和测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-114">Develop and test applications in a simulated Azure IaaS hybrid cloud environment.</span></span>
    
- <span data-ttu-id="7b0b6-115">创建计算机的测试配置（一些位于 TestLab 虚拟网络中，一些位于 XPrem 虚拟网络中），以模拟基于混合云的 IT 工作负荷。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-115">Create test configurations of computers, some within the TestLab virtual network and some within the XPrem virtual network, to simulate hybrid cloud-based IT workloads.</span></span>
    
<span data-ttu-id="7b0b6-116">设置此测试环境包含三个主要阶段：</span><span class="sxs-lookup"><span data-stu-id="7b0b6-116">There are three major phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="7b0b6-117">配置 TestLab 虚拟网络。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-117">Configure the TestLab virtual network.</span></span>
    
2. <span data-ttu-id="7b0b6-118">创建跨界虚拟网络。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-118">Create the cross-premises virtual network.</span></span>
    
3. <span data-ttu-id="7b0b6-119">配置 DC2。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-119">Configure DC2.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7b0b6-120">此配置需要付费的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-120">This configuration requires a paid Azure subscription.</span></span> 

<span data-ttu-id="7b0b6-121">利用生成的环境，可以通过额外的[测试实验室指南](m365-enterprise-test-lab-guides.md)或自行测试 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-121">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="7b0b6-123">单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-123">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-the-testlab-virtual-network"></a><span data-ttu-id="7b0b6-124">第 1 阶段：配置 TestLab 虚拟网络</span><span class="sxs-lookup"><span data-stu-id="7b0b6-124">Phase 1: Configure the TestLab virtual network</span></span>

<span data-ttu-id="7b0b6-125">请按[模拟企业基础配置](simulated-ent-base-configuration-microsoft-365-enterprise.md)的**第 1 阶段**中的说明操作，在名为 TestLab 的 Azure 虚拟网络中配置 DC1、APP1 和 CLIENT1 计算机。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-125">Use the instructions in **Phase 1** of the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to configure the DC1, APP1, and CLIENT1 computers in the Azure virtual network named TestLab.</span></span>
  
<span data-ttu-id="7b0b6-126">当前配置如下。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-126">This is your current configuration.</span></span> 
  
![Azure 中的模拟企业基础配置](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a><span data-ttu-id="7b0b6-128">第 2 阶段：创建 XPrem 虚拟网络</span><span class="sxs-lookup"><span data-stu-id="7b0b6-128">Phase 2: Create the XPrem virtual network</span></span>

<span data-ttu-id="7b0b6-129">在此阶段，你需要创建和配置新的 XPrem 虚拟网络，然后通过 VNet 对等关系将其连接到 TestLab 虚拟网络。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-129">In this phase, you create and configure the new XPrem virtual network and then connect it to the TestLab virtual network with VNet peering.</span></span>
  
<span data-ttu-id="7b0b6-130">首先，在本地计算机上启动 Azure PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-130">First, start an Azure PowerShell prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b0b6-p102">下面的命令集使用最新版 Azure PowerShell。请参阅 [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)（Azure PowerShell cmdlet 使用入门）。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-p102">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="7b0b6-133">使用此命令登录 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-133">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="7b0b6-134">使用此命令获取订阅名称。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-134">Get your subscription name using this command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="7b0b6-p103">设置 Azure 订阅。使用正确的名称替换引号内的所有内容（包括 \< 和 > 字符）。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-p103">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="7b0b6-137">接下来，创建 XPrem 虚拟网络，然后使用这些命令通过网络安全组保护此虚拟网络。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-137">Next, create the XPrem virtual network and protect it with a network security group with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$Testnet=New-AzVirtualNetworkSubnetConfig -Name "Testnet" -AddressPrefix 192.168.0.0/24
New-AzVirtualNetwork -Name "XPrem" -ResourceGroupName $rgName -Location $locName -AddressPrefix 192.168.0.0/16 -Subnet $Testnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
$nsg=Get-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "Testnet" -AddressPrefix 192.168.0.0/24 -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="7b0b6-138">接下来，使用下面这些命令在 TestLab 和 XPrem VNet 之间创建 VNet 对等关系。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-138">Next, you create the VNet peering relationship between the TestLab and XPrem VNets with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

<span data-ttu-id="7b0b6-139">当前配置如下。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-139">This is your current configuration.</span></span> 
  
![第 2 阶段的模拟跨界虚拟网络测试环境，包含 XPrem VNet 和 VNet 对等关系](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a><span data-ttu-id="7b0b6-141">第 3 阶段：配置 DC2</span><span class="sxs-lookup"><span data-stu-id="7b0b6-141">Phase 3: Configure DC2</span></span>

<span data-ttu-id="7b0b6-142">在此阶段，你需要在 XPrem 虚拟网络中创建 DC2 虚拟机，然后将其配置为副本域控制器。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-142">In this phase, you create the DC2 virtual machine in the XPrem virtual network and then configure it as a replica domain controller.</span></span>
  
<span data-ttu-id="7b0b6-p104">首先，创建 DC2 虚拟机。在本地计算机上的 Azure PowerShell 命令提示符处，运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-p104">First, create a virtual machine for DC2. Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<your resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name XPrem -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC2-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC2-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 192.168.0.4
$vm=New-AzVMConfig -VMName DC2 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC2."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC2 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC2-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC2-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC2-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="7b0b6-145">接下来，在 [Azure 门户](https://portal.azure.com)中使用本地管理员帐户名称和密码连接到新的 DC2 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-145">Next, connect to the new DC2 virtual machine from the [Azure portal](https://portal.azure.com) using its local administrator account name and password.</span></span>
  
<span data-ttu-id="7b0b6-p105">接下来，将 Windows 防火墙规则配置为允许通信以进行基本的连接测试。在 DC 2 上的管理员级别 Windows PowerShell 命令提示符处，运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-p105">Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing. From an administrator-level Windows PowerShell command prompt on DC2, run these commands.</span></span> 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

<span data-ttu-id="7b0b6-p106">ping 命令应获得从 IP 地址 10.0.0.4 发出的四个成功响应。这是跨 VNet 对等关系的通信测试。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-p106">The ping command should result in four successful replies from IP address 10.0.0.4. This is a test of traffic across the VNet peering relationship.</span></span> 
  
<span data-ttu-id="7b0b6-150">接下来，在 DC2 上的 Windows PowerShell 命令提示符处，使用下面的命令将额外的数据磁盘添加为新卷，驱动器号为 F:。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-150">Next, add the extra data disk as a new volume with the drive letter F: with this command from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="7b0b6-p107">接下来，将 DC2 配置为 corp.contoso.com 域的副本域控制器。在 DC2 上的 Windows PowerShell 命令提示符处，运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-p107">Next, configure DC2 as a replica domain controller for the corp.contoso.com domain. Run these commands from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

<span data-ttu-id="7b0b6-153">请注意，系统会提示你输入 CORP\\User1 密码和目录服务还原模式 (DSRM) 密码，并重启 DC2。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-153">Note that you are prompted to supply both the CORP\\User1 password and a Directory Services Restore Mode (DSRM) password, and to restart DC2.</span></span> 
  
<span data-ttu-id="7b0b6-p108">至此，XPrem 虚拟网络已拥有自己的 DNS 服务器 (DC2)。你必须将 XPrem 虚拟网络配置为使用此 DNS 服务器。在本地计算机上的 Azure PowerShell 命令提示符处，运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-p108">Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server. Run these commands from the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

<span data-ttu-id="7b0b6-p109">在本地计算机上的 Azure 门户中，使用 CORP\\User1 凭据连接到 DC1。要配置 CORP 域以便计算机和用户可以使用其本地域控制器进行身份验证，请在 DC1 上的管理员级别 Windows PowerShell 命令提示符处，运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-p109">From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials. To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

<span data-ttu-id="7b0b6-158">当前配置如下。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-158">This is your current configuration.</span></span> 
  
![第 3 阶段的模拟跨界虚拟网络测试环境，XPrem VNet 中有 DC2 虚拟机](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="7b0b6-160">此时，你的模拟 Azure 混合云环境就可供测试了。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-160">Your simulated Azure hybrid cloud environment is now ready for testing.</span></span>
  
<span data-ttu-id="7b0b6-161">现在可以试验 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="7b0b6-161">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="7b0b6-162">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7b0b6-162">Next steps</span></span>

<span data-ttu-id="7b0b6-163">浏览下面这些附加的一系列测试实验室指南：</span><span class="sxs-lookup"><span data-stu-id="7b0b6-163">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="7b0b6-164">标识</span><span class="sxs-lookup"><span data-stu-id="7b0b6-164">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="7b0b6-165">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="7b0b6-165">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="7b0b6-166">信息保护</span><span class="sxs-lookup"><span data-stu-id="7b0b6-166">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="7b0b6-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b0b6-167">See also</span></span>

[<span data-ttu-id="7b0b6-168">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="7b0b6-168">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7b0b6-169">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="7b0b6-169">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7b0b6-170">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="7b0b6-170">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
