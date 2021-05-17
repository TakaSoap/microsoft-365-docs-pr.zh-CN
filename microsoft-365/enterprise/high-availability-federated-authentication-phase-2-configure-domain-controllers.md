---
title: 高可用性联合身份验证阶段 2 配置域控制器
ms.author: josephd
author: JoeDavies-MSFT
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
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: 摘要：在 Microsoft Azure 中为 Microsoft 365 的高可用性联合身份验证配置域控制器和目录同步服务器。
ms.openlocfilehash: 751d332ce5f5606fe5f833182f002a1f4b6f29ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909806"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a><span data-ttu-id="81a24-103">高可用性联合身份验证阶段 2：配置域控制器</span><span class="sxs-lookup"><span data-stu-id="81a24-103">High availability federated authentication Phase 2: Configure domain controllers</span></span>

<span data-ttu-id="81a24-104">在部署 Azure 基础结构服务中的 Microsoft 365 联合身份验证的高可用性的这一阶段，在 Azure 虚拟网络中配置两个域控制器和目录同步服务器。</span><span class="sxs-lookup"><span data-stu-id="81a24-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you configure two domain controllers and the directory synchronization server in the Azure virtual network.</span></span> <span data-ttu-id="81a24-105">然后用于身份验证的客户端 Web 请求可以在 Azure 虚拟网络中进行身份验证，而不是将通过站点到站点 VPN 连接的该身份验证流量发送到本地网络。</span><span class="sxs-lookup"><span data-stu-id="81a24-105">Client web requests for authentication can then be authenticated in the Azure virtual network, rather than sending that authentication traffic across the site-to-site VPN connection to your on-premises network.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81a24-106">Active Directory 联合身份验证服务 (AD FS) 无法使用 Azure Active Directory (Azure AD) 替代 Active Directory 域服务 (AD DS) 域控制器。</span><span class="sxs-lookup"><span data-stu-id="81a24-106">Active Directory Federation Services (AD FS) cannot use Azure Active Directory (Azure AD) as a substitute for Active Directory Domain Services (AD DS) domain controllers.</span></span> 
  
<span data-ttu-id="81a24-107">必须先完成此阶段，然后才能进入阶段 [3：配置 AD FS 服务器](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="81a24-107">You must complete this phase before moving on to [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="81a24-108">有关 [所有阶段，请参阅在 Azure 中为 Microsoft 365](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) 部署高可用性联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="81a24-108">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a><span data-ttu-id="81a24-109">在 Azure 中创建域控制器虚拟机</span><span class="sxs-lookup"><span data-stu-id="81a24-109">Create the domain controller virtual machines in Azure</span></span>

<span data-ttu-id="81a24-110">首先，需要填写表 M 的 **虚拟机名称** 列，并根据需要在 **最小大小** 列修改虚拟机大小。</span><span class="sxs-lookup"><span data-stu-id="81a24-110">First, you need to fill out the **Virtual machine name** column of Table M and modify virtual machine sizes as needed in the **Minimum size** column.</span></span>
  
|<span data-ttu-id="81a24-111">**项**</span><span class="sxs-lookup"><span data-stu-id="81a24-111">**Item**</span></span>|<span data-ttu-id="81a24-112">**虚拟机名称**</span><span class="sxs-lookup"><span data-stu-id="81a24-112">**Virtual machine name**</span></span>|<span data-ttu-id="81a24-113">**库图像**</span><span class="sxs-lookup"><span data-stu-id="81a24-113">**Gallery image**</span></span>|<span data-ttu-id="81a24-114">**存储类型**</span><span class="sxs-lookup"><span data-stu-id="81a24-114">**Storage type**</span></span>|<span data-ttu-id="81a24-115">**最小大小**</span><span class="sxs-lookup"><span data-stu-id="81a24-115">**Minimum size**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81a24-116">1.</span><span class="sxs-lookup"><span data-stu-id="81a24-116">1.</span></span>  <br/> |![线条](../media/Common-Images/TableLine.png) <span data-ttu-id="81a24-118">（第一个域控制器，例如 DC1）</span><span class="sxs-lookup"><span data-stu-id="81a24-118">(first domain controller, example DC1)</span></span>  <br/> |<span data-ttu-id="81a24-119">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="81a24-119">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="81a24-120">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="81a24-120">Standard_LRS</span></span>  <br/> |<span data-ttu-id="81a24-121">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="81a24-121">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="81a24-122">2.</span><span class="sxs-lookup"><span data-stu-id="81a24-122">2.</span></span>  <br/> |![线条](../media/Common-Images/TableLine.png) <span data-ttu-id="81a24-124">（第二个域控制器，例如 DC2）</span><span class="sxs-lookup"><span data-stu-id="81a24-124">(second domain controller, example DC2)</span></span>  <br/> |<span data-ttu-id="81a24-125">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="81a24-125">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="81a24-126">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="81a24-126">Standard_LRS</span></span>  <br/> |<span data-ttu-id="81a24-127">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="81a24-127">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="81a24-128">3.</span><span class="sxs-lookup"><span data-stu-id="81a24-128">3.</span></span>  <br/> |![线条](../media/Common-Images/TableLine.png) <span data-ttu-id="81a24-130"> (目录同步服务器，示例 DS1) </span><span class="sxs-lookup"><span data-stu-id="81a24-130">(directory synchronization server, example DS1)</span></span>  <br/> |<span data-ttu-id="81a24-131">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="81a24-131">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="81a24-132">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="81a24-132">Standard_LRS</span></span>  <br/> |<span data-ttu-id="81a24-133">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="81a24-133">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="81a24-134">4.</span><span class="sxs-lookup"><span data-stu-id="81a24-134">4.</span></span>  <br/> |![线条](../media/Common-Images/TableLine.png) <span data-ttu-id="81a24-136"> (第一个 AD FS 服务器，例如 ADFS1) </span><span class="sxs-lookup"><span data-stu-id="81a24-136">(first AD FS server, example ADFS1)</span></span>  <br/> |<span data-ttu-id="81a24-137">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="81a24-137">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="81a24-138">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="81a24-138">Standard_LRS</span></span>  <br/> |<span data-ttu-id="81a24-139">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="81a24-139">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="81a24-140">5.</span><span class="sxs-lookup"><span data-stu-id="81a24-140">5.</span></span>  <br/> |![线条](../media/Common-Images/TableLine.png) <span data-ttu-id="81a24-142"> (个 AD FS 服务器，例如 ADFS2) </span><span class="sxs-lookup"><span data-stu-id="81a24-142">(second AD FS server, example ADFS2)</span></span>  <br/> |<span data-ttu-id="81a24-143">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="81a24-143">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="81a24-144">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="81a24-144">Standard_LRS</span></span>  <br/> |<span data-ttu-id="81a24-145">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="81a24-145">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="81a24-146">6.</span><span class="sxs-lookup"><span data-stu-id="81a24-146">6.</span></span>  <br/> |![线条](../media/Common-Images/TableLine.png) <span data-ttu-id="81a24-148"> (第一个 Web 应用程序代理服务器，例如 WEB1) </span><span class="sxs-lookup"><span data-stu-id="81a24-148">(first web application proxy server, example WEB1)</span></span>  <br/> |<span data-ttu-id="81a24-149">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="81a24-149">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="81a24-150">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="81a24-150">Standard_LRS</span></span>  <br/> |<span data-ttu-id="81a24-151">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="81a24-151">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="81a24-152">7.</span><span class="sxs-lookup"><span data-stu-id="81a24-152">7.</span></span>  <br/> |![线条](../media/Common-Images/TableLine.png) <span data-ttu-id="81a24-154"> (第二个 Web 应用程序代理服务器，例如 WEB2) </span><span class="sxs-lookup"><span data-stu-id="81a24-154">(second web application proxy server, example WEB2)</span></span>  <br/> |<span data-ttu-id="81a24-155">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="81a24-155">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="81a24-156">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="81a24-156">Standard_LRS</span></span>  <br/> |<span data-ttu-id="81a24-157">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="81a24-157">Standard_D2</span></span>  <br/> |
   
 <span data-ttu-id="81a24-158">**表 M - Azure 中用于 Microsoft 365 的高可用性联合身份验证的虚拟机**</span><span class="sxs-lookup"><span data-stu-id="81a24-158">**Table M - Virtual machines for the high availability federated authentication for Microsoft 365 in Azure**</span></span>
  
<span data-ttu-id="81a24-159">有关虚拟机大小的完整列表，请参阅[虚拟机的大小](/azure/virtual-machines/virtual-machines-windows-sizes)。</span><span class="sxs-lookup"><span data-stu-id="81a24-159">For the complete list of virtual machine sizes, see [Sizes for virtual machines](/azure/virtual-machines/virtual-machines-windows-sizes).</span></span>
  
<span data-ttu-id="81a24-160">以下 Azure PowerShell 命令块可创建两个域控制器的虚拟机。</span><span class="sxs-lookup"><span data-stu-id="81a24-160">The following Azure PowerShell command block creates the virtual machines for the two domain controllers.</span></span> <span data-ttu-id="81a24-161">指定变量的值，删除 \< and > 字符。</span><span class="sxs-lookup"><span data-stu-id="81a24-161">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="81a24-162">请注意，此 Azure PowerShell 命令块使用下表中的值：</span><span class="sxs-lookup"><span data-stu-id="81a24-162">Note that this Azure PowerShell command block uses values from the following tables:</span></span>
  
- <span data-ttu-id="81a24-163">表 M，用于虚拟机</span><span class="sxs-lookup"><span data-stu-id="81a24-163">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="81a24-164">表 R，用于资源组</span><span class="sxs-lookup"><span data-stu-id="81a24-164">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="81a24-165">表 V，用于虚拟网络设置</span><span class="sxs-lookup"><span data-stu-id="81a24-165">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="81a24-166">表 S，用于子网</span><span class="sxs-lookup"><span data-stu-id="81a24-166">Table S, for your subnets</span></span>
    
- <span data-ttu-id="81a24-167">表 I，用于静态 IP 地址</span><span class="sxs-lookup"><span data-stu-id="81a24-167">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="81a24-168">表 A（针对可用性集）</span><span class="sxs-lookup"><span data-stu-id="81a24-168">Table A, for your availability sets</span></span>
    
<span data-ttu-id="81a24-169">回想一下，你在阶段 [1：](high-availability-federated-authentication-phase-1-configure-azure.md)配置 Azure 中定义了表 R、V、S、I 和 A。</span><span class="sxs-lookup"><span data-stu-id="81a24-169">Recall that you defined Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="81a24-170">[!注意] 下面的命令集使用最新版 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="81a24-170">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="81a24-171">请参阅 [Azure PowerShell 入门](/powershell/azure/get-started-azureps)。</span><span class="sxs-lookup"><span data-stu-id="81a24-171">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="81a24-172">提供所有正确值后，在 Azure PowerShell 提示符处或本地计算机的 PowerShell 集成脚本环境 (ISE) 上运行生成块。</span><span class="sxs-lookup"><span data-stu-id="81a24-172">When you have supplied all the correct values, run the resulting block at the Azure PowerShell prompt or in the PowerShell Integrated Script Environment (ISE) on your local computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="81a24-173">若要根据自定义设置生成可运行的 PowerShell 命令块，请使用此 Microsoft [Excel 配置工作簿](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="81a24-173">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="81a24-p105">由于这些虚拟机用于 Intranet 应用程序，所以不会为它们分配公用 IP 地址或 DNS 域名称标签，也不会将它们公开到 Internet。但是，这也意味着你无法从 Azure 门户与它们进行连接。查看虚拟机的属性时“连接”选项不可用。使用远程桌面连接附件或另一个远程桌面工具连接使用其专用 IP 地址或 Intranet DNS 名称的虚拟机。</span><span class="sxs-lookup"><span data-stu-id="81a24-p105">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
## <a name="configure-the-first-domain-controller"></a><span data-ttu-id="81a24-178">配置第一个域控制器</span><span class="sxs-lookup"><span data-stu-id="81a24-178">Configure the first domain controller</span></span>

<span data-ttu-id="81a24-p106">使用你选择的远程桌面客户端并创建到第一个域控制器虚拟机的远程桌面连接。使用其 Intranet DNS 或计算机名称以及本地管理员帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="81a24-p106">Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="81a24-181">接下来，通过以下命令将额外的数据磁盘添加到第一个域控制器Windows PowerShell第一个域控制器虚拟机上的命令 **提示符中：**</span><span class="sxs-lookup"><span data-stu-id="81a24-181">Next, add the extra data disk to the first domain controller with this command from a Windows PowerShell command prompt **on the first domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="81a24-182">接下来，使用 **ping** 命令对组织网络中的资源名称和 IP 地址执行 ping 操作，测试第一个域控制器到组织网络中的位置的连接。</span><span class="sxs-lookup"><span data-stu-id="81a24-182">Next, test the first domain controller's connectivity to locations on your organization network by using the **ping** command to ping names and IP addresses of resources on your organization network.</span></span>
  
<span data-ttu-id="81a24-p107">此过程确保 DNS 名称解析正常进行（已为该虚拟机正确配置本地 DNS 服务器），并可以向/从跨本地虚拟网络发送数据。如果这个基本测试失败，请与你的 IT 部门联系，来解决 DNS 名称解析和数据包传递问题。</span><span class="sxs-lookup"><span data-stu-id="81a24-p107">This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network. If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.</span></span>
  
<span data-ttu-id="81a24-185">接下来，从第一个域控制器的 Windows PowerShell 命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="81a24-185">Next, from the Windows PowerShell command prompt on the first domain controller, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

<span data-ttu-id="81a24-p108">系统将提示你提供域管理员帐户的凭据。计算机将重新启动。</span><span class="sxs-lookup"><span data-stu-id="81a24-p108">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
## <a name="configure-the-second-domain-controller"></a><span data-ttu-id="81a24-188">配置第二个域控制器</span><span class="sxs-lookup"><span data-stu-id="81a24-188">Configure the second domain controller</span></span>

<span data-ttu-id="81a24-p109">使用你选择的远程桌面客户端并创建到第二个域控制器虚拟机的远程桌面连接。使用其 Intranet DNS 或计算机名称以及本地管理员帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="81a24-p109">Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="81a24-191">接下来，您需要通过以下命令将额外的数据磁盘添加到第二个域控制器Windows PowerShell域控制器虚拟机上的命令 **提示符中**：</span><span class="sxs-lookup"><span data-stu-id="81a24-191">Next, you need to add the extra data disk to the second domain controller with this command from a Windows PowerShell command prompt **on the second domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="81a24-192">接下来，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="81a24-192">Next, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

<span data-ttu-id="81a24-p110">系统将提示你提供域管理员帐户的凭据。计算机将重新启动。</span><span class="sxs-lookup"><span data-stu-id="81a24-p110">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
<span data-ttu-id="81a24-195">接下来，需要为虚拟网络更新 DNS 服务器，以便 Azure 为虚拟机分配两个新域控制器的 IP 地址，将它们用作其 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="81a24-195">Next, you need to update the DNS servers for your virtual network so that Azure assigns virtual machines the IP addresses of the two new domain controllers to use as their DNS servers.</span></span> <span data-ttu-id="81a24-196">填写变量，然后在本地计算机上从Windows PowerShell命令提示符运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="81a24-196">Fill in the variables and then run these commands from a Windows PowerShell command prompt on your local computer:</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

<span data-ttu-id="81a24-p112">请注意，我们重新启动两个域控制器，这样不会为它们配置本地 DNS 服务器作为 DNS 服务器。因为这两个控制器本身就是 DNS 服务器，因此在升级为域控制器后会自动为它们配置本地 DNS 服务器作为 DNS 转发器。</span><span class="sxs-lookup"><span data-stu-id="81a24-p112">Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers. Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.</span></span>
  
<span data-ttu-id="81a24-p113">接下来，我们需要创建一个 Active Directory 复制站点以确保 Azure 虚拟网络中的服务器使用本地域控制器。使用域管理员帐户连接到任一域控制器，从管理员级 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="81a24-p113">Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers. Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:</span></span>
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a><span data-ttu-id="81a24-201">配置目录同步服务器</span><span class="sxs-lookup"><span data-stu-id="81a24-201">Configure the directory synchronization server</span></span>

<span data-ttu-id="81a24-202">使用你选择的远程桌面客户端，并创建到目录同步服务器虚拟机的远程桌面连接。</span><span class="sxs-lookup"><span data-stu-id="81a24-202">Use the remote desktop client of your choice and create a remote desktop connection to the directory synchronization server virtual machine.</span></span> <span data-ttu-id="81a24-203">使用其 Intranet DNS 或计算机名称以及本地管理员帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="81a24-203">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="81a24-204">接下来，在命令提示符下使用这些命令，Windows PowerShell AD DS 域。</span><span class="sxs-lookup"><span data-stu-id="81a24-204">Next, join it to the appropriate AD DS domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="81a24-205">以下是因成功完成这一阶段后生成的配置，包含占位符计算机名称。</span><span class="sxs-lookup"><span data-stu-id="81a24-205">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="81a24-206">**阶段 2：Azure 中高可用性联合身份验证基础结构的域控制器和目录同步服务器**</span><span class="sxs-lookup"><span data-stu-id="81a24-206">**Phase 2: The domain controllers and directory synchronization server for your high availability federated authentication infrastructure in Azure**</span></span>

![Azure 中具有域控制器的高可用性 Microsoft 365 联合身份验证基础结构的第 2 阶段](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a><span data-ttu-id="81a24-208">后续步骤</span><span class="sxs-lookup"><span data-stu-id="81a24-208">Next step</span></span>

<span data-ttu-id="81a24-209">使用 [阶段 3：配置 AD FS 服务器](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) 以继续配置此工作负载。</span><span class="sxs-lookup"><span data-stu-id="81a24-209">Use [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81a24-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81a24-210">See Also</span></span>

[<span data-ttu-id="81a24-211">在 Azure 中为 Microsoft 365 部署高可用性联合身份验证</span><span class="sxs-lookup"><span data-stu-id="81a24-211">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="81a24-212">Microsoft 365 开发/测试环境的联合身份</span><span class="sxs-lookup"><span data-stu-id="81a24-212">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="81a24-213">Microsoft 365 解决方案和体系结构中心</span><span class="sxs-lookup"><span data-stu-id="81a24-213">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)