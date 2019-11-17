---
title: 适用于 Microsoft 365 的模拟企业基础配置
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用本测试实验室指南，创建针对 Microsoft 365 企业版的模拟企业测试环境。
ms.openlocfilehash: 5faa6857de42049cbcfc237e3e617de294794530
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640384"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="508ec-103">模拟企业基础配置</span><span class="sxs-lookup"><span data-stu-id="508ec-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="508ec-104">本文分步介绍了如何创建适用于 Microsoft 365 企业版 的简化环境，其中包括：</span><span class="sxs-lookup"><span data-stu-id="508ec-104">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="508ec-105">Microsoft 365 E5 试用版或付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-105">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="508ec-106">连接到 Internet 的简化组织 Intranet，包含 Azure 虚拟网络中的三个虚拟机（DC1、APP1 和 CLIENT1）。</span><span class="sxs-lookup"><span data-stu-id="508ec-106">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![模拟企业基础配置](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="508ec-108">利用生成的环境，可以通过额外的[测试实验室指南](m365-enterprise-test-lab-guides.md)或自行测试 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="508ec-108">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="508ec-110">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="508ec-110">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="508ec-111">第 1 阶段：创建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="508ec-111">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="508ec-112">在该阶段，要在 Azure 基础结构服务中构建模拟 Intranet，包括 Active Directory 域服务 (AD DS) 域控制器、应用程序服务器和客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="508ec-112">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="508ec-113">你将在额外的 [Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)中使用这些计算机来配置和演示混合标识和其他功能。</span><span class="sxs-lookup"><span data-stu-id="508ec-113">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="508ec-114">方法 1：使用 Azure 资源管理器模板构建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="508ec-114">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="508ec-p101">在此方法中，你可以使用 Azure 资源管理器 (ARM) 模板来构建模拟 Intranet。ARM 模板中包含有关创建 Azure 网络基础结构、虚拟机及其配置的所有说明。</span><span class="sxs-lookup"><span data-stu-id="508ec-p101">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet. ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="508ec-117">部署该模板之前，请通读“[模板自述文件](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)”页面且准备好以下信息：</span><span class="sxs-lookup"><span data-stu-id="508ec-117">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="508ec-p102">测试环境的公共 DNS 域名 (testlab.\<你的公共域名>)。你将需要在“**自定义部署**”页面的“**域名**”字段中输入此名称。</span><span class="sxs-lookup"><span data-stu-id="508ec-p102">The public DNS domain name of your test environment (testlab.\<your public domain>). You’ll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="508ec-p103">虚拟机公共 IP 地址 URL 的 DNS 标签前缀。你将需要在“**自定义部署**”页面的“**Dns 标签前缀**”字段中输入此标签。</span><span class="sxs-lookup"><span data-stu-id="508ec-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You’ll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="508ec-122">通读说明后，在“[模板自述文件](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)”页面上单击“**部署到 Azure**”，以开始进行部署。</span><span class="sxs-lookup"><span data-stu-id="508ec-122">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="508ec-123">通过 ARM 模板构建的模拟 Intranet 需要付费 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-123">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="508ec-124">模板完成后，会生成以下配置。</span><span class="sxs-lookup"><span data-stu-id="508ec-124">Here is your configuration after the template is complete.</span></span>

![Azure 基础结构服务中的模拟 Intranet](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="508ec-126">方法 2：使用 Azure PowerShell 构建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="508ec-126">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="508ec-127">在此方法中，你可以使用 Windows PowerShell 和 Azure PowerShell 模块来构建网络基础结构、虚拟机及其配置。</span><span class="sxs-lookup"><span data-stu-id="508ec-127">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="508ec-p104">如果想要体验通过 PowerShell 一次使用一个步骤创建 Azure 基础结构元素的过程，则可以使用此方法。然后可以自定义 PowerShell 命令块，以便自行在 Azure 中部署其他虚拟机。</span><span class="sxs-lookup"><span data-stu-id="508ec-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="508ec-130">步骤 1：创建 DC1</span><span class="sxs-lookup"><span data-stu-id="508ec-130">Step 1: Create DC1</span></span>

<span data-ttu-id="508ec-131">在这一步，我们会创建 Azure 虚拟网络并添加 DC1（一台用作 AD DS 域的域控制器的虚拟机）。</span><span class="sxs-lookup"><span data-stu-id="508ec-131">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="508ec-132">首先，在本地计算机上启动 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="508ec-132">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="508ec-p105">下面的命令集使用最新版 Azure PowerShell。请参阅 [Azure PowerShell cmdlet 使用入门](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)</span><span class="sxs-lookup"><span data-stu-id="508ec-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="508ec-135">使用以下命令登录 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="508ec-135">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="508ec-136">使用以下命令获得订阅名称。</span><span class="sxs-lookup"><span data-stu-id="508ec-136">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="508ec-p106">设置 Azure 订阅。将引号内的所有内容（包括 < 和 > 字符）都替换为正确的名称。</span><span class="sxs-lookup"><span data-stu-id="508ec-p106">Set your Azure subscription. Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="508ec-p107">接下来，为模拟企业测试实验室新建一个资源组。若要确定唯一资源组名称，请运行下面的命令，以列出现有资源组。</span><span class="sxs-lookup"><span data-stu-id="508ec-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="508ec-p108">运行下面这些命令，以新建资源组。将引号内的所有内容（包括 < 和 > 字符）都替换为正确的名称。</span><span class="sxs-lookup"><span data-stu-id="508ec-p108">Create your new resource group with these commands. Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="508ec-p109">接下来，创建托管模拟企业环境的公司网络子网的 TestLab 虚拟网络，并使用网络安全组来保护它。填写资源组名称，并在本地计算机上的 PowerShell 命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="508ec-p109">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group. Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="508ec-145">接下来，创建 DC1 虚拟机，并将它配置为 **testlab.**\<你的公共域> AD DS 域的域控制器，以及 TestLab 虚拟网络中虚拟机的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="508ec-145">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain> AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="508ec-146">例如，如果公共域名是 **<span>contoso</span>.com**，DC1 虚拟机将是 **<span>testlab</span>.contoso.com** 域的域控制器。</span><span class="sxs-lookup"><span data-stu-id="508ec-146">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="508ec-147">若要为 DC1 创建 Azure 虚拟机，请填写资源组名称，并在本地计算机上的 PowerShell 命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="508ec-147">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="508ec-p111">系统将提示你为 DC1 上的本地管理员帐户输入用户名和密码。使用强密码，并在安全位置记录名称和密码。</span><span class="sxs-lookup"><span data-stu-id="508ec-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="508ec-150">接下来，连接到 DC1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="508ec-150">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="508ec-151">在 [Azure 门户](https://portal.azure.com)中，单击“**资源组”>** [新资源组的名称] \*\* > DC1 >“连接\*\*”。</span><span class="sxs-lookup"><span data-stu-id="508ec-151">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="508ec-p112">在打开的窗格中，单击“**下载 RDP 文件**”。打开下载的 DC1.rdp 文件，然后单击“**连接**”。</span><span class="sxs-lookup"><span data-stu-id="508ec-p112">In the open pane, click **Download RDP file**. Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="508ec-154">指定 DC1 本地管理员帐户名：</span><span class="sxs-lookup"><span data-stu-id="508ec-154">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="508ec-155">对于 Windows 7：</span><span class="sxs-lookup"><span data-stu-id="508ec-155">For Windows 7:</span></span>
    
     <span data-ttu-id="508ec-p113">在“Windows 安全性”\*\*\*\* 对话框中，单击“使用另一个帐户”\*\*\*\*。在“用户名称”\*\*\*\* 中，键入 **DC1\\**[本地管理员帐户名称]</span><span class="sxs-lookup"><span data-stu-id="508ec-p113">In the **Windows Security** dialog box, click **Use another account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="508ec-158">对于 Windows 8 或 Windows 10：</span><span class="sxs-lookup"><span data-stu-id="508ec-158">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="508ec-p114">在“Windows 安全性”\*\*\*\* 对话框中，单击“更多选择”\*\*\*\*，然后单击“使用不同帐户”\*\*\*\*。在“用户名”\*\*\*\* 中，键入 **DC1\\**[本地管理员帐户名称]。</span><span class="sxs-lookup"><span data-stu-id="508ec-p114">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="508ec-161">在“密码”\*\*\*\* 中，键入本地管理员帐户密码，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-161">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="508ec-162">出现提示时，请单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-162">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="508ec-163">接下来，在 DC1 上的管理员级 Windows PowerShell 命令提示符处运行下面的命令，将额外的数据磁盘添加为新卷，驱动器号为 F:。</span><span class="sxs-lookup"><span data-stu-id="508ec-163">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="508ec-p115">接下来，将 DC1 配置为 **testlab.**\<公共域名> 域的域控制器和 DNS 服务器。指定公共域名，删除 \< 和 > 字符，再在 DC1 上的管理员级 Windows PowerShell 命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="508ec-p115">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain> domain. Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="508ec-p116">需要指定安全模式管理员密码。将此密码存储到安全位置。</span><span class="sxs-lookup"><span data-stu-id="508ec-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="508ec-168">请注意，这些命令可能会花几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="508ec-168">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="508ec-169">DC1 重启后，重新连接到 DC1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="508ec-169">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="508ec-170">在 [Azure 门户](https://portal.azure.com)中，单击“**资源组 >** [你的资源组名称] **> DC1 > 连接**”。</span><span class="sxs-lookup"><span data-stu-id="508ec-170">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="508ec-171">运行下载的 DC1.rdp 文件，再单击“连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-171">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="508ec-p117">在“Windows 安全性”\*\*\*\* 内，单击“使用另一帐户”\*\*\*\*。在“用户名”\*\*\*\* 中，键入“TESTLAB\\*\*\*\*[本地管理员帐户名]”。</span><span class="sxs-lookup"><span data-stu-id="508ec-p117">In **Windows Security**, click **Use another account**. In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="508ec-174">在“密码”\*\*\*\* 中，键入本地管理员帐户密码，再单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-174">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="508ec-175">当出现提示时，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-175">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="508ec-p118">接下来，在 Active Directory 中创建用于登录 TESTLAB 域成员计算机的用户帐户。在管理员级 Windows PowerShell 命令提示符处，运行下面的命令。</span><span class="sxs-lookup"><span data-stu-id="508ec-p118">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers. Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="508ec-p119">请注意，此命令会提示你提供 User1 帐户密码。由于这个帐户要用于所有 TESTLAB 域成员计算机的远程桌面连接，因此选择使用强密码。记录 User1 帐户密码，并将它存储到安全位置。</span><span class="sxs-lookup"><span data-stu-id="508ec-p119">Note that this command prompts you to supply the User1 account password. Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password. Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="508ec-p120">接下来，将新的 User1 帐户配置为域、企业和架构管理员。在管理员级 Windows PowerShell 命令提示符处，运行下面的命令。</span><span class="sxs-lookup"><span data-stu-id="508ec-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab"+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="508ec-183">关闭与 DC1 的远程桌面会话，再使用 TESTLAB\\User1 帐户重新连接。</span><span class="sxs-lookup"><span data-stu-id="508ec-183">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="508ec-184">接下来，若要允许 Ping 工具有流量，请在管理员级 Windows PowerShell 命令提示符处运行下面的命令。</span><span class="sxs-lookup"><span data-stu-id="508ec-184">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="508ec-185">当前配置如下。</span><span class="sxs-lookup"><span data-stu-id="508ec-185">This is your current configuration.</span></span>
  
![模拟企业基础配置的步骤 1](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="508ec-187">步骤 2：配置 APP1</span><span class="sxs-lookup"><span data-stu-id="508ec-187">Step 2: Configure APP1</span></span>

<span data-ttu-id="508ec-188">在这一步，创建和配置 APP1，这是初始提供 Web 和文件共享服务的应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="508ec-188">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="508ec-189">若要为 APP1 创建 Azure 虚拟机，请填写资源组名称，并在本地计算机上的命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="508ec-189">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="508ec-190">接下来，使用 APP1 本地管理员帐户名称和密码连接到 APP1 虚拟机，然后打开 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="508ec-190">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="508ec-191">若要检查 APP1 和 DC1 之间的名称解析和网络通信，请运行 **ping dc1.testlab.**\<公共域名> 命令，并验证是否有四个回复。</span><span class="sxs-lookup"><span data-stu-id="508ec-191">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command and verify that there are four replies.</span></span>
  
<span data-ttu-id="508ec-192">接下来，在 Windows PowerShell 提示符处，运行下面这些命令，将 APP1 虚拟机加入 TESTLAB 域。</span><span class="sxs-lookup"><span data-stu-id="508ec-192">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="508ec-193">请注意，运行 **Add-Computer** 命令后，必须提供 TESTLAB\\User1 域帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="508ec-193">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="508ec-194">在 APP1 重启后，使用 TESTLAB\\User1 帐户连接到它，再打开管理员级 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="508ec-194">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="508ec-195">接下来，在 APP1 上的管理员级 Windows PowerShell 命令提示符处，运行下面的命令，将 APP1 设置为 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="508ec-195">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="508ec-196">接下来，运行下面这些 PowerShell 命令，在 APP1 上的文件夹中创建共享文件夹和文本文件。</span><span class="sxs-lookup"><span data-stu-id="508ec-196">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="508ec-197">当前配置如下。</span><span class="sxs-lookup"><span data-stu-id="508ec-197">This is your current configuration.</span></span>
  
![模拟企业基础配置的步骤 2](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="508ec-199">步骤 3：配置 CLIENT1</span><span class="sxs-lookup"><span data-stu-id="508ec-199">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="508ec-200">在这一步，创建和配置 CLIENT1，这是 Intranet 上的典型笔记本电脑、平板电脑或台式计算机。</span><span class="sxs-lookup"><span data-stu-id="508ec-200">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="508ec-p121">下面的命令集会创建运行 Windows Server 2016 Datacenter 的 CLIENT1，可对所有类型的 Azure 订阅执行此操作。若有基于 Visual Studio 的 Azure 订阅，可以通过 [Azure 门户](https://portal.azure.com)创建运行 Windows 10 的 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="508ec-p121">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have an Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="508ec-203">若要为 CLIENT1 创建 Azure 虚拟机，请填写资源组名称，并在本地计算机上的命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="508ec-203">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="508ec-204">接下来，使用 CLIENT1 本地管理员帐户名称和密码连接到 CLIENT1 虚拟机，然后打开管理员级别 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="508ec-204">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="508ec-205">若要检查 CLIENT1 和 DC1 之间的名称解析和网络通信，请在 Windows PowerShell 命令提示符处运行 **ping dc1.testlab.**\<公共域名> 命令，并验证是否有四个回复。</span><span class="sxs-lookup"><span data-stu-id="508ec-205">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="508ec-206">接下来，在 Windows PowerShell 提示符处，运行下面这些命令，将 CLIENT1 虚拟机加入 TESTLAB 域。</span><span class="sxs-lookup"><span data-stu-id="508ec-206">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="508ec-207">请注意，运行 **Add-Computer** 命令后，必须提供 TESTLAB\\User1 域帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="508ec-207">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="508ec-208">在 CLIENT1 重启后，使用 TESTLAB\\User1 帐户名和密码连接到它，再打开管理员级 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="508ec-208">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="508ec-209">接下来，验证能否从 CLIENT1 中的 APP1 访问 Web 和文件共享资源。</span><span class="sxs-lookup"><span data-stu-id="508ec-209">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="508ec-210">在服务器管理器的树窗格中，单击“**本地服务器**”。</span><span class="sxs-lookup"><span data-stu-id="508ec-210">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="508ec-211">在“CLIENT1 的属性”\*\*\*\* 中，单击“IE 增强的安全配置”\*\*\*\* 旁边的“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-211">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="508ec-212">在“Internet Explorer 增强的安全性配置”\*\*\*\* 中，为**管理员**和**用户**单击“关闭”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-212">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="508ec-213">在“开始”屏幕中，依次单击“Internet Explorer”\*\*\*\* 和“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-213">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="508ec-p122">在地址栏中，键入“http<span>://</span>app1.testab.\*\*\*\*\<公共域名/\*\*\*\*”，再按 ENTER。应该会看到 APP1 的默认 Internet Information Services 网页。</span><span class="sxs-lookup"><span data-stu-id="508ec-p122">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER. You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="508ec-216">从桌面任务栏中，单击“文件资源管理器”图标。</span><span class="sxs-lookup"><span data-stu-id="508ec-216">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="508ec-p123">在地址栏中，键入 **\\\\app1\\Files**，然后按 ENTER 键。应该会看到带有文件共享文件夹内容的文件夹窗口。</span><span class="sxs-lookup"><span data-stu-id="508ec-p123">In the address bar, type **\\\\app1\\Files**, and then press ENTER. You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="508ec-p124">在“文件”\*\*\*\* 共享文件夹窗口中，双击“Example.txt”\*\*\*\* 文件。应该会看到 Example.txt 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="508ec-p124">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="508ec-221">关闭“example.txt - 记事本”\*\*\*\* 和“文件”\*\*\*\* 共享文件夹窗口。</span><span class="sxs-lookup"><span data-stu-id="508ec-221">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="508ec-222">当前配置如下。</span><span class="sxs-lookup"><span data-stu-id="508ec-222">This is your current configuration.</span></span>
  
![模拟企业基础配置的步骤 3](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="508ec-224">第 2 阶段：创建 Microsoft 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="508ec-224">Phase 2: Create your Microsoft 365 E5 subscriptions</span></span>

<span data-ttu-id="508ec-p125">在此阶段，你将创建一个新的 Microsoft 365 E5 订阅，该订阅使用新的 Azure AD 租户（独立于生产订阅）。可通过两种方式实现此目的：</span><span class="sxs-lookup"><span data-stu-id="508ec-p125">In this phase, you create a new Microsoft 365 E5 subscription that use a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="508ec-227">使用 Microsoft 365 E5 的试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-227">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="508ec-p126">Microsoft 365 E5 试用版订阅的有效期为 30 天，可轻松延长至 60 天。试用版订阅到期后，你必须将其转换为付费版订阅或创建新的试用版订阅。创建新的试用版订阅意味着你将保留配置，其中可能包含复杂的方案。</span><span class="sxs-lookup"><span data-stu-id="508ec-p126">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscriptions or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="508ec-231">使用包含少量许可证的 Microsoft 365 E5 独立生产订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-231">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="508ec-p127">虽然这会产生额外费用，但可确保拥有不会到期的有效测试环境，可用于尝试功能、配置和方案。可以长期使用相同的测试环境，用于概念验证、平级演示和管理以及应用程序开发和测试。建议使用这种方法。</span><span class="sxs-lookup"><span data-stu-id="508ec-p127">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire. You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing. This is the recommended method.</span></span>

<span data-ttu-id="508ec-235">要启动 Microsoft 365 E5 试用版订阅，你首先需要一个虚构公司名称和一个新的 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="508ec-235">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="508ec-p128">我们建议你将公司名称 Contoso 的变体用作你的公司名称，它是 Microsoft 示例内容中使用的虚构公司，但这并不是必需的。在此记录虚构的公司名称：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="508ec-p128">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="508ec-p129">要注册新的 Microsoft 帐户，请转到 [https://outlook.com](https://outlook.com)，然后使用新的电子邮件帐户和地址创建一个帐户。此帐户将用于注册 Office 365。</span><span class="sxs-lookup"><span data-stu-id="508ec-p129">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="508ec-240">在此记录新帐户的名字和姓氏：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="508ec-240">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="508ec-241">在此记录新的电子邮件帐户地址：![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="508ec-241">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="508ec-242">注册 Office 365 E5 试用订阅</span><span class="sxs-lookup"><span data-stu-id="508ec-242">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="508ec-243">我们首先使用 Office 365 E5 试用版订阅，然后向其添加 Microsoft 365 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-243">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

1. <span data-ttu-id="508ec-244">对于模拟的企业 Office 365 开发/测试环境，请使用 CORP\User1 帐户从 Azure 门户连接到 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="508ec-244">For the simulated enterprise Office 365 dev/test environment, connect to CLIENT1 with the CORP\User1 account from the Azure portal.</span></span>  <span data-ttu-id="508ec-245">从“开始”屏幕中，运行 Microsoft Edge 然后转到 [https://aka.ms/e5trial](https://aka.ms/e5trial)。</span><span class="sxs-lookup"><span data-stu-id="508ec-245">From the Start screen, run Microsoft Edge and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="508ec-246">在“欢迎，很高兴认识你”\*\*\*\* 页上，请指定：</span><span class="sxs-lookup"><span data-stu-id="508ec-246">On the **Welcome, let's get to know you** page, specify:</span></span>
    
  - <span data-ttu-id="508ec-247">你的实际位置</span><span class="sxs-lookup"><span data-stu-id="508ec-247">Your physical location</span></span>
    
  - <span data-ttu-id="508ec-248">你新的 Microsoft 帐户的名字和姓氏</span><span class="sxs-lookup"><span data-stu-id="508ec-248">The first and last name of your new Microsoft account</span></span>
    
  - <span data-ttu-id="508ec-249">你新的电子邮件帐户地址</span><span class="sxs-lookup"><span data-stu-id="508ec-249">Your new email account address</span></span>
    
  - <span data-ttu-id="508ec-250">业务电话号码</span><span class="sxs-lookup"><span data-stu-id="508ec-250">A business phone number</span></span>
    
  - <span data-ttu-id="508ec-251">你虚构的公司名称</span><span class="sxs-lookup"><span data-stu-id="508ec-251">Your fictional company name</span></span>
    
  - <span data-ttu-id="508ec-252">规模达 250-999 人的组织</span><span class="sxs-lookup"><span data-stu-id="508ec-252">An organization size of 250-999 people</span></span>
    
3. <span data-ttu-id="508ec-253">单击“只需再执行一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-253">Click **Just one more step**.</span></span>
    
4. <span data-ttu-id="508ec-254">在“**创建你的用户 ID**”页上，基于你新的电子邮件地址、@ 符号之后你的虚构公司（删除名称中的所有空格）键入用户名，然后为此新的 Office 365 帐户键入密码（两次）。</span><span class="sxs-lookup"><span data-stu-id="508ec-254">On the **Create your user ID** page, type a user name based on your new email address, your fictional company after the @ sign (remove all spaces in the name), then a password (twice) for this new Office 365 account.</span></span>
    
    <span data-ttu-id="508ec-255">将你键入的密码记录在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="508ec-255">Record the password that you typed in a secure location.</span></span>
    
    <span data-ttu-id="508ec-256">在此记录你的虚构公司名称，将其称为“组织名称”\*\*\*\*：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="508ec-256">Record your fictional company name, to be referred to as the **organization name**, here: ![](./media/Common-Images/TableLine.png)</span></span>
    
5. <span data-ttu-id="508ec-257">单击“创建我的帐户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-257">Click **Create my account**.</span></span>
    
6. <span data-ttu-id="508ec-p131">在“证明你不是机器人”\*\*\*\* 页上，键入可发短信的手机号码，然后单击“给我发短信”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-p131">On the **Prove. You're. Not. A. Robot.** page, type the phone number of your text-capable phone, and then click **Text me**.</span></span>
    
7. <span data-ttu-id="508ec-260">键入短信中收到的验证代码，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-260">Type the verification code from the received text message, and then click **Next**.</span></span>
    
8. <span data-ttu-id="508ec-261">在此记录登录页面 URL（选择并复制）：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="508ec-261">Record the sign-in page URL here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span>
    
9. <span data-ttu-id="508ec-262">在此记录用户 ID（选择并复制）：![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="508ec-262">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="508ec-263">此值将被称为“Office 365 全局管理员名称”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-263">This value will be referred to as the **Office 365 global administrator name**.</span></span>
    
10. <span data-ttu-id="508ec-264">看到“你已准备就绪”\*\*\*\* 时，请单击它。</span><span class="sxs-lookup"><span data-stu-id="508ec-264">When you see **You're ready to go**, click it.</span></span>
    
11. <span data-ttu-id="508ec-265">在下一页，等到 Office 365 完成设置并且显示所有标题。</span><span class="sxs-lookup"><span data-stu-id="508ec-265">On the next page, wait until Office 365 completes setting up and all the tiles are available.</span></span>
    
<span data-ttu-id="508ec-266">你应可看到 Office 365 门户主页，可从该页访问 Office 服务和 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="508ec-266">You should see main Office 365 portal page from which you can access Office services and the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="508ec-267">我们为你创建了 Office 365 的试用版订阅，以便你的开发/测试环境具有与你当前拥有的任何付费版订阅分开的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="508ec-267">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="508ec-268">这样分开意味着你可在测试租户中添加和删除用户和组，而不影响生产订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-268">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
### <a name="configure-your-office-365-e5-trial-subscription"></a><span data-ttu-id="508ec-269">配置 Office 365 E5 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="508ec-269">Phase 3: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="508ec-270">接下来，配置包含其他用户的 Office 365 E5 订阅，并为这些用户分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="508ec-270">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="508ec-271">按照[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) 中的说明，使用 CLIENT1 虚拟机中的 Azure Active Directory PowerShell for Graph 模块连接到 Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-271">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from:</span></span>
    
<span data-ttu-id="508ec-272">在“Windows PowerShell 凭据请求”对话框中，键入 Office 365 全局管理员名称（示例：jdoe@contosotoycompany.onmicrosoft.com）和密码。</span><span class="sxs-lookup"><span data-stu-id="508ec-272">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="508ec-273">填写组织名称（示例：contosotoycompany）、你所在位置的两位字符的国家/地区代码以及通用帐户密码，然后 PowerShell 提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="508ec-273">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="508ec-274">此处使用公用密码旨在自动配置开发/测试环境，简化配置过程。</span><span class="sxs-lookup"><span data-stu-id="508ec-274">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="508ec-275">显然，对于生产订阅，这是非常不鼓励的。</span><span class="sxs-lookup"><span data-stu-id="508ec-275">Obviously, this is highly discouraged for production subscriptions.</span></span> 

#### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="508ec-276">记录关键信息供将来参考</span><span class="sxs-lookup"><span data-stu-id="508ec-276">Record key information for future reference</span></span>

<span data-ttu-id="508ec-277">不妨打印这篇文章，以便记录在 30 天的 Office 365 试用版订阅期内需要对此环境使用的特定信息。</span><span class="sxs-lookup"><span data-stu-id="508ec-277">You might want to print this article to record the specific values that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="508ec-278">可以轻松地将该订阅的试用期再延长 30 天。</span><span class="sxs-lookup"><span data-stu-id="508ec-278">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="508ec-279">对于永久性开发/测试环境，请创建一个包含单独 Azure AD 租户和少量许可证的新付费订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-279">For a permanent dev/test environment, create a new paid subscription with a small number of licenses.</span></span>

<span data-ttu-id="508ec-280">请记录以下值：</span><span class="sxs-lookup"><span data-stu-id="508ec-280">Record these values:</span></span>
  
- <span data-ttu-id="508ec-281">Office 365 全局管理员名称：![](./media/Common-Images/TableLine.png).onmicrosoft.com（在第 2 阶段的第 9 步中）</span><span class="sxs-lookup"><span data-stu-id="508ec-281">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="508ec-282">此外，还应将此帐户的密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="508ec-282">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="508ec-283">试用订阅组织名称：![](./media/Common-Images/TableLine.png)（在第 2 阶段的第 4 步中）</span><span class="sxs-lookup"><span data-stu-id="508ec-283">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="508ec-284">要列出 User 2、User 3、User 4 和 User 5 的帐户，从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="508ec-284">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="508ec-285">在此记录帐户名称：</span><span class="sxs-lookup"><span data-stu-id="508ec-285">Record the account names here:</span></span>
    
  - <span data-ttu-id="508ec-286">User 2 的帐户名称：user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="508ec-286">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="508ec-287">User 3 的帐户名称：user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="508ec-287">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="508ec-288">User 4 的帐户名称：user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="508ec-288">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="508ec-289">User 5 的帐户名称：user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="508ec-289">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="508ec-290">此外，在安全位置记录这些帐户的公用密码。</span><span class="sxs-lookup"><span data-stu-id="508ec-290">Also record the passwords for these accounts in a secure location.</span></span>
   

#### <a name="using-an-office-365-e5-devtest-environment"></a><span data-ttu-id="508ec-291">使用 Office 365 E5 开发/测试环境</span><span class="sxs-lookup"><span data-stu-id="508ec-291">Using an Office 365 E5 dev/test environment</span></span>

<span data-ttu-id="508ec-292">如果你只需要一个 Office 365 开发/测试环境，则可以在此处停止。</span><span class="sxs-lookup"><span data-stu-id="508ec-292">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="508ec-293">有关同时适用于 Office 365 和 Microsoft 365 的其他测试实验室指南，请参阅 [Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="508ec-293">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="508ec-294">添加 Microsoft 365 E5 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="508ec-294">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="508ec-295">接下来，可注册 Microsoft 365 E5 试用版订阅，并将其添加到 Office 365 E5 试用版订阅所在的组织中。</span><span class="sxs-lookup"><span data-stu-id="508ec-295">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="508ec-296">首先，请添加 Microsoft 365 E5 试用版订阅并向全局管理员帐户分配一个 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="508ec-296">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="508ec-297">通过 Internet 浏览器的专用实例，使用全局管理员帐户凭据登录 [https://admin.microsoft.com](https://admin.microsoft.com) 上的 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="508ec-297">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="508ec-298">在“**Microsoft 365 管理中心**”页面上的左侧导航栏中，单击“**计费 > 购买服务**”。</span><span class="sxs-lookup"><span data-stu-id="508ec-298">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="508ec-299">在“**购买服务**”页面上，找到“**Microsoft 365 E5**”项目。</span><span class="sxs-lookup"><span data-stu-id="508ec-299">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="508ec-300">将鼠标指针悬停在该项目上方并单击“**开始免费试用**”。</span><span class="sxs-lookup"><span data-stu-id="508ec-300">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="508ec-301">在“**Microsoft 365 E5 试用版**”页面上，选择接收短信或通话，输入你的电话号码，然后单击“**发短信给我**”或“**打电话给我**”。</span><span class="sxs-lookup"><span data-stu-id="508ec-301">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="508ec-302">在“确认订单”页上，单击“立即试用”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-302">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="508ec-303">在“订单签收”页中，单击“继续”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="508ec-303">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="508ec-304">在 Microsoft 365 管理中心中，单击“**活动用户**”，然后单击管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="508ec-304">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="508ec-305">对于**产品许可证**，请单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="508ec-305">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="508ec-306">关闭 Office 365 企业版 E5 的许可证，并打开 Microsoft 365 E5 的许可证。</span><span class="sxs-lookup"><span data-stu-id="508ec-306">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="508ec-307">单击“**保存 > 关闭 > 关闭**”。</span><span class="sxs-lookup"><span data-stu-id="508ec-307">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="508ec-308">接下来，对其他所有帐户（用户 2、用户 3、用户 4 和用户 5）重复执行上面过程的第 8 步到第 11 步。</span><span class="sxs-lookup"><span data-stu-id="508ec-308">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="508ec-309">Microsoft 365 E5 试用版订阅的有效期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="508ec-309">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="508ec-310">对于永久性测试环境，请将此试用版订阅转换为包含少量许可证的付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-310">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
### <a name="results"></a><span data-ttu-id="508ec-311">结果</span><span class="sxs-lookup"><span data-stu-id="508ec-311">Results</span></span>

<span data-ttu-id="508ec-312">测试环境现在包含：</span><span class="sxs-lookup"><span data-stu-id="508ec-312">Your test environment now has:</span></span>
  
- <span data-ttu-id="508ec-313">Microsoft 365 E5 试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="508ec-313">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="508ec-314">你所有相应的用户帐户都被允许使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="508ec-314">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="508ec-315">模拟和简化的 Intranet。</span><span class="sxs-lookup"><span data-stu-id="508ec-315">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="508ec-316">最终配置如下。</span><span class="sxs-lookup"><span data-stu-id="508ec-316">This is your final configuration.</span></span>
  
![模拟企业基础配置的第 2 阶段](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="508ec-318">现在可以试验 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="508ec-318">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="508ec-319">后续步骤</span><span class="sxs-lookup"><span data-stu-id="508ec-319">Next steps</span></span>

<span data-ttu-id="508ec-320">浏览下面这些附加的一系列测试实验室指南：</span><span class="sxs-lookup"><span data-stu-id="508ec-320">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="508ec-321">标识</span><span class="sxs-lookup"><span data-stu-id="508ec-321">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="508ec-322">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="508ec-322">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="508ec-323">信息保护</span><span class="sxs-lookup"><span data-stu-id="508ec-323">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="508ec-324">另请参阅</span><span class="sxs-lookup"><span data-stu-id="508ec-324">See also</span></span>

[<span data-ttu-id="508ec-325">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="508ec-325">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="508ec-326">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="508ec-326">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="508ec-327">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="508ec-327">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
