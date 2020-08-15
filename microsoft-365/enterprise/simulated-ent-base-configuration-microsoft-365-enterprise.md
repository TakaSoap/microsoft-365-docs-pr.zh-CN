---
title: 适用于 Microsoft 365 的模拟企业基础配置
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用此测试实验室指南创建适用于企业的 Microsoft 365 的模拟企业测试环境。
ms.openlocfilehash: 9f4cbb300946109368759d6ec8f1120332e1ed92
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685672"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="4b38f-103">模拟企业基础配置</span><span class="sxs-lookup"><span data-stu-id="4b38f-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="4b38f-104">*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="4b38f-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4b38f-105">本文为您提供了创建适用于企业的 Microsoft 365 的简化环境的分步说明，其中包括：</span><span class="sxs-lookup"><span data-stu-id="4b38f-105">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 for enterprise that includes:</span></span>

- <span data-ttu-id="4b38f-106">Microsoft 365 E5 试用版或付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="4b38f-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="4b38f-107">连接到 Internet 的简化组织 Intranet，包含 Azure 虚拟网络中的三个虚拟机（DC1、APP1 和 CLIENT1）。</span><span class="sxs-lookup"><span data-stu-id="4b38f-107">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![模拟企业基础配置](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="4b38f-109">您可以使用生成的环境，通过其他[测试实验室指南](m365-enterprise-test-lab-guides.md)或在您自己的环境中测试[适用于企业的 Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="4b38f-109">You can use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="4b38f-111">转到 [microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) For the microsoft 365 For 企业测试实验室指南堆栈中的所有文章。</span><span class="sxs-lookup"><span data-stu-id="4b38f-111">Go to [Microsoft 365 for enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="4b38f-112">第 1 阶段：创建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="4b38f-112">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="4b38f-113">在该阶段，要在 Azure 基础结构服务中构建模拟 Intranet，包括 Active Directory 域服务 (AD DS) 域控制器、应用程序服务器和客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="4b38f-113">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="4b38f-114">您将在其他 [Microsoft 365 for 企业测试实验室指南](m365-enterprise-test-lab-guides.md) 中使用这些计算机来配置和演示混合身份和其他功能。</span><span class="sxs-lookup"><span data-stu-id="4b38f-114">You'll use these computers in additional [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="4b38f-115">方法 1：使用 Azure 资源管理器模板构建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="4b38f-115">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="4b38f-p101">在此方法中，你可以使用 Azure 资源管理器 (ARM) 模板来构建模拟 Intranet。ARM 模板中包含有关创建 Azure 网络基础结构、虚拟机及其配置的所有说明。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p101">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet. ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="4b38f-118">部署该模板之前，请通读“[模板自述文件](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)”页面且准备好以下信息：</span><span class="sxs-lookup"><span data-stu-id="4b38f-118">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="4b38f-p102">测试环境的公共 DNS 域名 (testlab.\<your public domain>)。你将需要在“**自定义部署**”页面的“**域名**”字段中输入此名称。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p102">The public DNS domain name of your test environment (testlab.\<your public domain>). You'll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="4b38f-p103">虚拟机公共 IP 地址 URL 的 DNS 标签前缀。你将需要在“**自定义部署**”页面的“**Dns 标签前缀**”字段中输入此标签。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="4b38f-123">通读说明后，在“[模板自述文件](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)”页面上单击“**部署到 Azure**”，以开始进行部署。</span><span class="sxs-lookup"><span data-stu-id="4b38f-123">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="4b38f-124">通过 ARM 模板构建的模拟 Intranet 需要付费 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="4b38f-124">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="4b38f-125">模板完成后，会生成以下配置。</span><span class="sxs-lookup"><span data-stu-id="4b38f-125">Here is your configuration after the template is complete.</span></span>

![Azure 基础结构服务中的模拟 Intranet](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="4b38f-127">方法 2：使用 Azure PowerShell 构建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="4b38f-127">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="4b38f-128">在此方法中，你可以使用 Windows PowerShell 和 Azure PowerShell 模块来构建网络基础结构、虚拟机及其配置。</span><span class="sxs-lookup"><span data-stu-id="4b38f-128">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="4b38f-p104">如果想要体验通过 PowerShell 一次使用一个步骤创建 Azure 基础结构元素的过程，则可以使用此方法。然后可以自定义 PowerShell 命令块，以便自行在 Azure 中部署其他虚拟机。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="4b38f-131">步骤 1：创建 DC1</span><span class="sxs-lookup"><span data-stu-id="4b38f-131">Step 1: Create DC1</span></span>

<span data-ttu-id="4b38f-132">在这一步，我们会创建 Azure 虚拟网络并添加 DC1（一台用作 AD DS 域的域控制器的虚拟机）。</span><span class="sxs-lookup"><span data-stu-id="4b38f-132">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="4b38f-133">首先，在本地计算机上启动 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="4b38f-133">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4b38f-p105">下面的命令集使用最新版 Azure PowerShell。请参阅 [Azure PowerShell cmdlet 使用入门](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)</span><span class="sxs-lookup"><span data-stu-id="4b38f-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="4b38f-136">使用以下命令登录 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="4b38f-136">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="4b38f-137">使用以下命令获得订阅名称。</span><span class="sxs-lookup"><span data-stu-id="4b38f-137">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="4b38f-p106">设置 Azure 订阅。将引号内的所有内容（包括 < 和 > 字符）都替换为正确的名称。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p106">Set your Azure subscription. Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="4b38f-p107">接下来，为模拟企业测试实验室新建一个资源组。若要确定唯一资源组名称，请运行下面的命令，以列出现有资源组。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="4b38f-p108">运行下面这些命令，以新建资源组。将引号内的所有内容（包括 < 和 > 字符）都替换为正确的名称。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p108">Create your new resource group with these commands. Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="4b38f-p109">接下来，创建托管模拟企业环境的公司网络子网的 TestLab 虚拟网络，并使用网络安全组来保护它。填写资源组名称，并在本地计算机上的 PowerShell 命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p109">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group. Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="4b38f-146">接下来，创建 DC1 虚拟机，并将它配置为 **testlab.**\<your public domain> AD DS 域的域控制器，</span><span class="sxs-lookup"><span data-stu-id="4b38f-146">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="4b38f-147">以及 TestLab 虚拟网络中虚拟机的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="4b38f-147">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="4b38f-148">例如，如果公共域名是 **<span>contoso</span>.com**，DC1 虚拟机将是 **<span>testlab</span>.contoso.com** 域的域控制器。</span><span class="sxs-lookup"><span data-stu-id="4b38f-148">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="4b38f-149">若要为 DC1 创建 Azure 虚拟机，请填写资源组名称，并在本地计算机上的 PowerShell 命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="4b38f-149">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
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

<span data-ttu-id="4b38f-p111">系统将提示你为 DC1 上的本地管理员帐户输入用户名和密码。使用强密码，并在安全位置记录名称和密码。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="4b38f-152">接下来，连接到 DC1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="4b38f-152">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="4b38f-153">在 [Azure 门户](https://portal.azure.com)中，单击“**资源组”>** [新资源组的名称] \*\* > DC1 >“连接\*\*”。</span><span class="sxs-lookup"><span data-stu-id="4b38f-153">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="4b38f-p112">在打开的窗格中，单击“**下载 RDP 文件**”。打开下载的 DC1.rdp 文件，然后单击“**连接**”。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p112">In the open pane, click **Download RDP file**. Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="4b38f-156">指定 DC1 本地管理员帐户名：</span><span class="sxs-lookup"><span data-stu-id="4b38f-156">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="4b38f-157">对于 Windows 7：</span><span class="sxs-lookup"><span data-stu-id="4b38f-157">For Windows 7:</span></span>
    
     <span data-ttu-id="4b38f-p113">在“Windows 安全性”\*\*\*\* 对话框中，单击“使用另一个帐户”\*\*\*\*。在“用户名称”\*\*\*\* 中，键入 **DC1\\**[本地管理员帐户名称]</span><span class="sxs-lookup"><span data-stu-id="4b38f-p113">In the **Windows Security** dialog box, click **Use another account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="4b38f-160">对于 Windows 8 或 Windows 10：</span><span class="sxs-lookup"><span data-stu-id="4b38f-160">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="4b38f-p114">在“Windows 安全性”\*\*\*\* 对话框中，单击“更多选择”\*\*\*\*，然后单击“使用不同帐户”\*\*\*\*。在“用户名”\*\*\*\* 中，键入 **DC1\\**[本地管理员帐户名称]。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p114">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="4b38f-163">在“密码”\*\*\*\* 中，键入本地管理员帐户密码，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b38f-163">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="4b38f-164">出现提示时，请单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b38f-164">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="4b38f-165">接下来，在 DC1 上的管理员级 Windows PowerShell 命令提示符处运行下面的命令，将额外的数据磁盘添加为新卷，驱动器号为 F:。</span><span class="sxs-lookup"><span data-stu-id="4b38f-165">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="4b38f-166">接下来，将 DC1 配置为 **testlab.**\<your public domain> 域的域控制器和 DNS 服务器</span><span class="sxs-lookup"><span data-stu-id="4b38f-166">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain></span></span> <span data-ttu-id="4b38f-167">。</span><span class="sxs-lookup"><span data-stu-id="4b38f-167">domain.</span></span> <span data-ttu-id="4b38f-168">指定你的公共域名，删除 \< and > 字符，然后在 DC1 的管理员级别 Windows PowerShell 命令提示符处运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="4b38f-168">Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="4b38f-p116">需要指定安全模式管理员密码。将此密码存储到安全位置。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="4b38f-171">请注意，这些命令可能会花几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="4b38f-171">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="4b38f-172">DC1 重启后，重新连接到 DC1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="4b38f-172">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="4b38f-173">在 [Azure 门户](https://portal.azure.com)中，单击“**资源组 >** [你的资源组名称] **> DC1 > 连接**”。</span><span class="sxs-lookup"><span data-stu-id="4b38f-173">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="4b38f-174">运行下载的 DC1.rdp 文件，再单击“连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b38f-174">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="4b38f-p117">在“Windows 安全性”\*\*\*\* 内，单击“使用另一帐户”\*\*\*\*。在“用户名”\*\*\*\* 中，键入“TESTLAB\\*\*\*\*[本地管理员帐户名]”。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p117">In **Windows Security**, click **Use another account**. In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="4b38f-177">在“密码”\*\*\*\* 中，键入本地管理员帐户密码，再单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b38f-177">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="4b38f-178">当出现提示时，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b38f-178">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="4b38f-p118">接下来，在 Active Directory 中创建用于登录 TESTLAB 域成员计算机的用户帐户。在管理员级 Windows PowerShell 命令提示符处，运行下面的命令。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p118">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers. Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="4b38f-p119">请注意，此命令会提示你提供 User1 帐户密码。由于这个帐户要用于所有 TESTLAB 域成员计算机的远程桌面连接，因此选择使用强密码。记录 User1 帐户密码，并将它存储到安全位置。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p119">Note that this command prompts you to supply the User1 account password. Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password. Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="4b38f-p120">接下来，将新的 User1 帐户配置为域、企业和架构管理员。在管理员级 Windows PowerShell 命令提示符处，运行下面的命令。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="4b38f-186">关闭与 DC1 的远程桌面会话，再使用 TESTLAB\\User1 帐户重新连接。</span><span class="sxs-lookup"><span data-stu-id="4b38f-186">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="4b38f-187">接下来，若要允许 Ping 工具有流量，请在管理员级 Windows PowerShell 命令提示符处运行下面的命令。</span><span class="sxs-lookup"><span data-stu-id="4b38f-187">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="4b38f-188">当前配置如下。</span><span class="sxs-lookup"><span data-stu-id="4b38f-188">This is your current configuration.</span></span>
  
![模拟企业基础配置的步骤 1](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="4b38f-190">步骤 2：配置 APP1</span><span class="sxs-lookup"><span data-stu-id="4b38f-190">Step 2: Configure APP1</span></span>

<span data-ttu-id="4b38f-191">在这一步，创建和配置 APP1，这是初始提供 Web 和文件共享服务的应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="4b38f-191">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="4b38f-192">若要为 APP1 创建 Azure 虚拟机，请填写资源组名称，并在本地计算机上的命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="4b38f-192">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="4b38f-193">接下来，使用 APP1 本地管理员帐户名称和密码连接到 APP1 虚拟机，然后打开 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="4b38f-193">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4b38f-194">若要检查 APP1 和 DC1 之间的名称解析和网络通信，请运行 **ping dc1.testlab.**\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="4b38f-194">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="4b38f-195">命令，并验证是否存在四个答复。</span><span class="sxs-lookup"><span data-stu-id="4b38f-195">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="4b38f-196">接下来，在 Windows PowerShell 提示符处，运行下面这些命令，将 APP1 虚拟机加入 TESTLAB 域。</span><span class="sxs-lookup"><span data-stu-id="4b38f-196">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="4b38f-197">请注意，运行 **Add-Computer** 命令后，必须提供 TESTLAB\\User1 域帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="4b38f-197">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="4b38f-198">在 APP1 重启后，使用 TESTLAB\\User1 帐户连接到它，再打开管理员级 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="4b38f-198">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4b38f-199">接下来，在 APP1 上的管理员级 Windows PowerShell 命令提示符处，运行下面的命令，将 APP1 设置为 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="4b38f-199">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="4b38f-200">接下来，运行下面这些 PowerShell 命令，在 APP1 上的文件夹中创建共享文件夹和文本文件。</span><span class="sxs-lookup"><span data-stu-id="4b38f-200">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="4b38f-201">当前配置如下。</span><span class="sxs-lookup"><span data-stu-id="4b38f-201">This is your current configuration.</span></span>
  
![模拟企业基础配置的步骤 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="4b38f-203">步骤 3：配置 CLIENT1</span><span class="sxs-lookup"><span data-stu-id="4b38f-203">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="4b38f-204">在这一步，创建和配置 CLIENT1，这是 Intranet 上的典型笔记本电脑、平板电脑或台式计算机。</span><span class="sxs-lookup"><span data-stu-id="4b38f-204">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="4b38f-p122">下面的命令集会创建运行 Windows Server 2016 Datacenter 的 CLIENT1，可对所有类型的 Azure 订阅执行此操作。若有基于 Visual Studio 的 Azure 订阅，可通过 [Azure 门户](https://portal.azure.com)创建运行 Windows 10 的 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p122">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="4b38f-207">若要为 CLIENT1 创建 Azure 虚拟机，请填写资源组名称，并在本地计算机上的命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="4b38f-207">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="4b38f-208">接下来，使用 CLIENT1 本地管理员帐户名称和密码连接到 CLIENT1 虚拟机，然后打开管理员级别 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="4b38f-208">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4b38f-209">若要检查 CLIENT1 和 DC1 之间的名称解析和网络通信，请在 Windows PowerShell 命令提示符处运行 **ping dc1.testlab.**\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="4b38f-209">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="4b38f-210">命令，并验证是否存在四个答复。</span><span class="sxs-lookup"><span data-stu-id="4b38f-210">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="4b38f-211">接下来，在 Windows PowerShell 提示符处，运行下面这些命令，将 CLIENT1 虚拟机加入 TESTLAB 域。</span><span class="sxs-lookup"><span data-stu-id="4b38f-211">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="4b38f-212">请注意，运行 **Add-Computer** 命令后，必须提供 TESTLAB\\User1 域帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="4b38f-212">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="4b38f-213">在 CLIENT1 重启后，使用 TESTLAB\\User1 帐户名和密码连接到它，再打开管理员级 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="4b38f-213">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="4b38f-214">接下来，验证能否从 CLIENT1 中的 APP1 访问 Web 和文件共享资源。</span><span class="sxs-lookup"><span data-stu-id="4b38f-214">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="4b38f-215">在服务器管理器的树窗格中，单击“**本地服务器**”。</span><span class="sxs-lookup"><span data-stu-id="4b38f-215">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="4b38f-216">在“CLIENT1 的属性”\*\*\*\* 中，单击“IE 增强的安全配置”\*\*\*\* 旁边的“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b38f-216">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="4b38f-217">在“Internet Explorer 增强的安全性配置”\*\*\*\* 中，为**管理员**和**用户**单击“关闭”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b38f-217">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="4b38f-218">在“开始”屏幕中，依次单击“Internet Explorer”\*\*\*\* 和“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b38f-218">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="4b38f-219">在地址栏中，键入 **http<span>://</span>app1.testab.**\<your public domain name>**/**，然后按 ENTER 键。</span><span class="sxs-lookup"><span data-stu-id="4b38f-219">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER.</span></span> <span data-ttu-id="4b38f-220">应该会看到 APP1 的默认 Internet Information Services 网页。</span><span class="sxs-lookup"><span data-stu-id="4b38f-220">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="4b38f-221">从桌面任务栏中，单击“文件资源管理器”图标。</span><span class="sxs-lookup"><span data-stu-id="4b38f-221">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="4b38f-p125">在地址栏中，键入 **\\\\app1\\Files**，然后按 ENTER 键。应该会看到带有文件共享文件夹内容的文件夹窗口。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p125">In the address bar, type **\\\\app1\\Files**, and then press ENTER. You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="4b38f-p126">在“文件”\*\*\*\* 共享文件夹窗口中，双击“Example.txt”\*\*\*\* 文件。应该会看到 Example.txt 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p126">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="4b38f-226">关闭“example.txt - 记事本”\*\*\*\* 和“文件”\*\*\*\* 共享文件夹窗口。</span><span class="sxs-lookup"><span data-stu-id="4b38f-226">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="4b38f-227">当前配置如下。</span><span class="sxs-lookup"><span data-stu-id="4b38f-227">This is your current configuration.</span></span>
  
![模拟企业基础配置的步骤 3](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="4b38f-229">第 2 阶段：创建 Microsoft 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="4b38f-229">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="4b38f-p127">在此阶段，你将创建一个新的 Microsoft 365 E5 订阅，该订阅使用新的 Azure AD 租户（独立于生产订阅）。可通过两种方式实现此目的：</span><span class="sxs-lookup"><span data-stu-id="4b38f-p127">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="4b38f-232">使用 Microsoft 365 E5 的试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="4b38f-232">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="4b38f-p128">Microsoft 365 E5 试用版订阅的有效期为 30 天，可轻松延长至 60 天。试用版订阅到期后，你必须将其转换为付费版订阅或创建新的试用版订阅。创建新的试用版订阅意味着你将保留配置，其中可能包含复杂的方案。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p128">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="4b38f-236">使用包含少量许可证的 Microsoft 365 E5 独立生产订阅。</span><span class="sxs-lookup"><span data-stu-id="4b38f-236">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="4b38f-p129">虽然这会产生额外费用，但可确保拥有不会到期的有效测试环境，可用于尝试功能、配置和方案。可以长期使用相同的测试环境，用于概念验证、平级演示和管理以及应用程序开发和测试。建议使用这种方法。</span><span class="sxs-lookup"><span data-stu-id="4b38f-p129">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire. You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing. This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="4b38f-240">注册 Office 365 E5 试用订阅</span><span class="sxs-lookup"><span data-stu-id="4b38f-240">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="4b38f-241">通过 CORP\User1 帐户从 Azure 门户连接到 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="4b38f-241">Connect to CLIENT1 with the CORP\User1 account from the Azure portal.</span></span>

<span data-ttu-id="4b38f-242">若要创建新的 Office 365 E5 试用版订阅，请按照“轻型基准配置测试实验室指南”[阶段 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4b38f-242">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="4b38f-243">若要配置新的 Office 365 E5 试用版订阅，请按照“轻型基准配置测试实验室指南”[阶段 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4b38f-243">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="4b38f-244">使用 Office 365 E5 测试环境</span><span class="sxs-lookup"><span data-stu-id="4b38f-244">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="4b38f-245">如果你只需要一个 Office 365 测试环境，则可以在此处停止。</span><span class="sxs-lookup"><span data-stu-id="4b38f-245">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="4b38f-246">有关适用于 Microsoft 365 和 Office 365 的其他测试实验室指南，请参阅适用于 [企业测试实验室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md) 。</span><span class="sxs-lookup"><span data-stu-id="4b38f-246">See [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Microsoft 365 and Office 365.</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="4b38f-247">添加 Microsoft 365 E5 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="4b38f-247">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="4b38f-248">若要使用 Microsoft 365 E5 试用版订阅并通过许可证配置用户帐户，请按照“轻型基准配置测试实验室指南”[阶段 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4b38f-248">To a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="4b38f-249">结果</span><span class="sxs-lookup"><span data-stu-id="4b38f-249">Results</span></span>

<span data-ttu-id="4b38f-250">测试环境现在包含：</span><span class="sxs-lookup"><span data-stu-id="4b38f-250">Your test environment now has:</span></span>
  
- <span data-ttu-id="4b38f-251">Microsoft 365 E5 试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="4b38f-251">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="4b38f-252">你所有相应的用户帐户都被允许使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="4b38f-252">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="4b38f-253">模拟和简化的 Intranet。</span><span class="sxs-lookup"><span data-stu-id="4b38f-253">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="4b38f-254">最终配置如下。</span><span class="sxs-lookup"><span data-stu-id="4b38f-254">This is your final configuration.</span></span>
  
![模拟企业基础配置的第 2 阶段](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="4b38f-256">现在，你可以试用 [Microsoft 365 for 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="4b38f-256">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="4b38f-257">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4b38f-257">Next steps</span></span>

<span data-ttu-id="4b38f-258">浏览下面这些附加的一系列测试实验室指南：</span><span class="sxs-lookup"><span data-stu-id="4b38f-258">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="4b38f-259">标识</span><span class="sxs-lookup"><span data-stu-id="4b38f-259">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="4b38f-260">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="4b38f-260">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="4b38f-261">信息保护</span><span class="sxs-lookup"><span data-stu-id="4b38f-261">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="4b38f-262">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b38f-262">See also</span></span>

[<span data-ttu-id="4b38f-263">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="4b38f-263">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4b38f-264">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="4b38f-264">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4b38f-265">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="4b38f-265">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
