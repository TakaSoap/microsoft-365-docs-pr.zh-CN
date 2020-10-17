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
ms.openlocfilehash: e66ec8c48e309daeb15aad5fcc475edcb2b8bb35
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487650"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="b683d-103">模拟企业基础配置</span><span class="sxs-lookup"><span data-stu-id="b683d-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="b683d-104">*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="b683d-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b683d-105">本文介绍如何为适用于企业的 Microsoft 365 创建简化的环境，其中包括：</span><span class="sxs-lookup"><span data-stu-id="b683d-105">This article describes how to create a simplified environment for Microsoft 365 for enterprise that includes:</span></span>

- <span data-ttu-id="b683d-106">Microsoft 365 E5 试用版或付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="b683d-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="b683d-107">连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络 (DC1、APP1 和 CLIENT1) 中的三个虚拟机组成。</span><span class="sxs-lookup"><span data-stu-id="b683d-107">A simplified organization intranet connected to the internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![模拟企业基础配置](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="b683d-109">创建简化的测试环境包含两个阶段：</span><span class="sxs-lookup"><span data-stu-id="b683d-109">Creating a simplified test environment involves two phases:</span></span>
- [<span data-ttu-id="b683d-110">第 1 阶段：创建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="b683d-110">Phase 1: Create a simulated intranet</span></span>](#phase-1-create-a-simulated-intranet)
- [<span data-ttu-id="b683d-111">第 2 阶段：创建 Microsoft 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="b683d-111">Phase 2: Create your Microsoft 365 E5 subscription</span></span>](#phase-2-create-your-microsoft-365-e5-subscription)

<span data-ttu-id="b683d-112">您可以使用生成的环境，通过其他[测试实验室指南](m365-enterprise-test-lab-guides.md)或在您自己的环境中测试[适用于企业的 Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="b683d-112">You can use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b683d-114">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b683d-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="b683d-115">第 1 阶段：创建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="b683d-115">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="b683d-116">在此阶段，在 Azure 基础结构服务中构建一个模拟的 intranet，其中包括 Active Directory 域服务 (AD DS) 域控制器、应用程序服务器和客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="b683d-116">In this phase, build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span>

<span data-ttu-id="b683d-117">您将在其他 [Microsoft 365 for 企业测试实验室指南](m365-enterprise-test-lab-guides.md) 中使用这些计算机来配置和演示混合身份和其他功能。</span><span class="sxs-lookup"><span data-stu-id="b683d-117">You'll use these computers in additional [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="b683d-118">方法 1：使用 Azure 资源管理器模板构建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="b683d-118">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="b683d-119">在此方法中，使用 Azure 资源管理器模板来构建模拟的 intranet。</span><span class="sxs-lookup"><span data-stu-id="b683d-119">In this method, you use an Azure Resource Manager template to build out the simulated intranet.</span></span> <span data-ttu-id="b683d-120">Azure 资源管理器模板包含创建 Azure 网络基础结构、虚拟机及其配置的所有说明。</span><span class="sxs-lookup"><span data-stu-id="b683d-120">Azure Resource Manager templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="b683d-121">部署模板之前，请阅读 [TEMPLATE README 页面](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) ，并准备好以下信息：</span><span class="sxs-lookup"><span data-stu-id="b683d-121">Before deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="b683d-122">您的测试环境的公共 DNS 域名 (testlab。 \<*your public domain*>) 。</span><span class="sxs-lookup"><span data-stu-id="b683d-122">The public DNS domain name of your test environment (testlab.\<*your public domain*>).</span></span> <span data-ttu-id="b683d-123">您将在 "**自定义部署**" 页的 "**域名**" 字段中输入此名称。</span><span class="sxs-lookup"><span data-stu-id="b683d-123">You'll enter this name in the **Domain Name** field of the **Custom deployment** page.</span></span>
- <span data-ttu-id="b683d-p103">虚拟机公共 IP 地址 URL 的 DNS 标签前缀。你将需要在“**自定义部署**”页面的“**Dns 标签前缀**”字段中输入此标签。</span><span class="sxs-lookup"><span data-stu-id="b683d-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="b683d-126">阅读完说明后，选择 "[模板自述文件" 页面](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems)上的 "**部署到 Azure** " 以开始使用。</span><span class="sxs-lookup"><span data-stu-id="b683d-126">After you read through the instructions, select **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="b683d-127">由 Azure 资源管理器模板生成的模拟 intranet 需要付费的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="b683d-127">The simulated intranet built by the Azure Resource Manager template requires a paid Azure subscription.</span></span>

<span data-ttu-id="b683d-128">模板完成后，您的配置将如下所示：</span><span class="sxs-lookup"><span data-stu-id="b683d-128">After the template is complete, your configuration looks like this:</span></span>

![Azure 基础结构服务中的模拟 Intranet](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="b683d-130">方法 2：使用 Azure PowerShell 构建模拟 Intranet</span><span class="sxs-lookup"><span data-stu-id="b683d-130">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="b683d-131">在此方法中，你可以使用 Windows PowerShell 和 Azure PowerShell 模块来构建网络基础结构、虚拟机及其配置。</span><span class="sxs-lookup"><span data-stu-id="b683d-131">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="b683d-p104">如果想要体验通过 PowerShell 一次使用一个步骤创建 Azure 基础结构元素的过程，则可以使用此方法。然后可以自定义 PowerShell 命令块，以便自行在 Azure 中部署其他虚拟机。</span><span class="sxs-lookup"><span data-stu-id="b683d-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="b683d-134">步骤 1：创建 DC1</span><span class="sxs-lookup"><span data-stu-id="b683d-134">Step 1: Create DC1</span></span>

<span data-ttu-id="b683d-135">在此步骤中，您将创建一个 Azure 虚拟网络并添加 DC1 （一个作为 AD DS 域的域控制器的虚拟机）。</span><span class="sxs-lookup"><span data-stu-id="b683d-135">In this step, you create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="b683d-136">首先，在本地计算机上启动 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="b683d-136">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b683d-p105">下面的命令集使用最新版 Azure PowerShell。请参阅 [Azure PowerShell cmdlet 使用入门](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)</span><span class="sxs-lookup"><span data-stu-id="b683d-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="b683d-139">使用以下命令登录 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="b683d-139">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="b683d-140">使用以下命令获得订阅名称。</span><span class="sxs-lookup"><span data-stu-id="b683d-140">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="b683d-141">设置 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="b683d-141">Set your Azure subscription.</span></span> <span data-ttu-id="b683d-142">使用正确的名称替换引号内的所有内容，包括尖括号 ( "<" 和 ">" ) 。</span><span class="sxs-lookup"><span data-stu-id="b683d-142">Replace everything within the quotation marks, including the angle brackets ("<" and ">"), with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="b683d-p107">接下来，为模拟企业测试实验室新建一个资源组。若要确定唯一资源组名称，请运行下面的命令，以列出现有资源组。</span><span class="sxs-lookup"><span data-stu-id="b683d-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="b683d-145">使用这些命令创建新的资源组。</span><span class="sxs-lookup"><span data-stu-id="b683d-145">Create your new resource group with these commands.</span></span> <span data-ttu-id="b683d-146">使用正确的名称替换引号内的所有内容（包括尖括号）。</span><span class="sxs-lookup"><span data-stu-id="b683d-146">Replace everything within the quotation marks, including the angle brackets, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="b683d-147">接下来，创建将承载模拟企业环境的企业网络子网的 TestLab 虚拟网络，并使用网络安全组对其进行保护。</span><span class="sxs-lookup"><span data-stu-id="b683d-147">Next, create the TestLab virtual network that will host the corporate network subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="b683d-148">填写您的资源组的名称，并在本地计算机上的 PowerShell 命令提示符处运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="b683d-148">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="b683d-149">接下来，创建 DC1 虚拟机，并将它配置为 **testlab.**\<your public domain> AD DS 域的域控制器，</span><span class="sxs-lookup"><span data-stu-id="b683d-149">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="b683d-150">以及 TestLab 虚拟网络中虚拟机的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="b683d-150">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="b683d-151">例如，如果公共域名是 **<span>contoso</span>.com**，DC1 虚拟机将是 **<span>testlab</span>.contoso.com** 域的域控制器。</span><span class="sxs-lookup"><span data-stu-id="b683d-151">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="b683d-152">若要为 DC1 创建 Azure 虚拟机，请填写资源组名称，并在本地计算机上的 PowerShell 命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="b683d-152">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="b683d-p111">系统将提示你为 DC1 上的本地管理员帐户输入用户名和密码。使用强密码，并在安全位置记录名称和密码。</span><span class="sxs-lookup"><span data-stu-id="b683d-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="b683d-155">接下来，连接到 DC1 虚拟机：</span><span class="sxs-lookup"><span data-stu-id="b683d-155">Next, connect to the DC1 virtual machine:</span></span>
  
1. <span data-ttu-id="b683d-156">在[Azure 门户](https://portal.azure.com)中，选择 **"资源组**" > <> > **DC1**Connect 中***的新资源组的名称***  >  **Connect**。</span><span class="sxs-lookup"><span data-stu-id="b683d-156">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <***the name of your new resource group***> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="b683d-157">在 "打开" 窗格中，选择 " **下载 RDP 文件**"。</span><span class="sxs-lookup"><span data-stu-id="b683d-157">In the open pane, select **Download RDP file**.</span></span> <span data-ttu-id="b683d-158">打开下载的 DC1 文件，然后选择 " **连接**"。</span><span class="sxs-lookup"><span data-stu-id="b683d-158">Open the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="b683d-159">指定 DC1 本地管理员帐户名：</span><span class="sxs-lookup"><span data-stu-id="b683d-159">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="b683d-160">对于 Windows 7：</span><span class="sxs-lookup"><span data-stu-id="b683d-160">For Windows 7:</span></span>
    
     <span data-ttu-id="b683d-161">在 " **Windows 安全性** " 对话框中，选择 " **使用其他帐户**"。</span><span class="sxs-lookup"><span data-stu-id="b683d-161">In the **Windows Security** dialog box, select **Use another account**.</span></span> <span data-ttu-id="b683d-162">在 "**用户名**" 中，输入\*\* \\ DC1\*\* < *本地管理员帐户名称*>。</span><span class="sxs-lookup"><span data-stu-id="b683d-162">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
   - <span data-ttu-id="b683d-163">对于 Windows 8 或 Windows 10：</span><span class="sxs-lookup"><span data-stu-id="b683d-163">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="b683d-164">在 " **Windows 安全性** " 对话框中，选择 " **更多选项**"，然后选择 " **使用其他帐户**"。</span><span class="sxs-lookup"><span data-stu-id="b683d-164">In the **Windows Security** dialog box, select **More choices**, and then select **Use a different account**.</span></span> <span data-ttu-id="b683d-165">在 "**用户名**" 中，输入\*\* \\ DC1\*\* < *本地管理员帐户名称*>。</span><span class="sxs-lookup"><span data-stu-id="b683d-165">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="b683d-166">在 " **密码**" 中，输入本地管理员帐户的密码，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b683d-166">In **Password**, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="b683d-167">出现提示时，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="b683d-167">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="b683d-168">接下来，在 DC1 上的管理员级 Windows PowerShell 命令提示符处运行下面的命令，将额外的数据磁盘添加为新卷，驱动器号为 F:。</span><span class="sxs-lookup"><span data-stu-id="b683d-168">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="b683d-169">接下来，将 DC1 配置为 **testlab.**\<*your public domain*> 域的域控制器和 DNS 服务器</span><span class="sxs-lookup"><span data-stu-id="b683d-169">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<*your public domain*></span></span> <span data-ttu-id="b683d-170">。</span><span class="sxs-lookup"><span data-stu-id="b683d-170">domain.</span></span> <span data-ttu-id="b683d-171">指定您的公共域名，删除尖括号，然后在 DC1 上的管理员级 Windows PowerShell 命令提示符处运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="b683d-171">Specify your public domain name, remove the angle brackets, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="b683d-p116">需要指定安全模式管理员密码。将此密码存储到安全位置。</span><span class="sxs-lookup"><span data-stu-id="b683d-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="b683d-174">请注意，这些命令可能会花几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="b683d-174">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="b683d-175">DC1 重启后，重新连接到 DC1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="b683d-175">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="b683d-176">在[Azure 门户](https://portal.azure.com)中，选择 **"资源**组" > <> > **DC1**Connect 中*的资源组名称*  >  **Connect**。</span><span class="sxs-lookup"><span data-stu-id="b683d-176">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <*your resource group name*> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="b683d-177">运行下载的 DC1 文件，然后选择 " **连接**"。</span><span class="sxs-lookup"><span data-stu-id="b683d-177">Run the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="b683d-178">在 " **Windows 安全性**" 中，选择 " **使用其他帐户**"。</span><span class="sxs-lookup"><span data-stu-id="b683d-178">In **Windows Security**, select **Use another account**.</span></span> <span data-ttu-id="b683d-179">在 "**用户名**" 中，输入\*\* \\ TESTLAB\*\* < *本地管理员帐户名称*>。</span><span class="sxs-lookup"><span data-stu-id="b683d-179">In **User name**, enter **TESTLAB\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="b683d-180">在 " **密码** " 框中，输入本地管理员帐户的密码，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b683d-180">In the **Password** box, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="b683d-181">出现提示时，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="b683d-181">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="b683d-182">接下来，在 Active Directory 中创建登录到 TESTLAB 域成员计算机时将使用的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b683d-182">Next, create a user account in Active Directory that will be used when signing in to TESTLAB domain member computers.</span></span> <span data-ttu-id="b683d-183">在管理员级别 Windows PowerShell 命令提示符中，运行此命令。</span><span class="sxs-lookup"><span data-stu-id="b683d-183">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="b683d-184">请注意，此命令会提示你提供用户 1 帐户密码。</span><span class="sxs-lookup"><span data-stu-id="b683d-184">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="b683d-185">此帐户将用于所有 TESTLAB 域成员计算机的远程桌面连接，因此请选择一个强密码。</span><span class="sxs-lookup"><span data-stu-id="b683d-185">This account will be used for remote desktop connections for all TESTLAB domain member computers, so choose a strong password.</span></span> <span data-ttu-id="b683d-186">记录 User1 帐户密码并将其存储在安全位置。</span><span class="sxs-lookup"><span data-stu-id="b683d-186">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="b683d-p120">接下来，将新的 User1 帐户配置为域、企业和架构管理员。在管理员级 Windows PowerShell 命令提示符处，运行下面的命令。</span><span class="sxs-lookup"><span data-stu-id="b683d-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="b683d-189">关闭与 DC1 的远程桌面会话，再使用 TESTLAB\\User1 帐户重新连接。</span><span class="sxs-lookup"><span data-stu-id="b683d-189">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="b683d-190">接下来，若要允许 Ping 工具有流量，请在管理员级 Windows PowerShell 命令提示符处运行下面的命令。</span><span class="sxs-lookup"><span data-stu-id="b683d-190">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="b683d-191">您的当前配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="b683d-191">Your current configuration looks like this:</span></span>
  
![模拟企业基础配置的步骤 1](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="b683d-193">步骤 2：配置 APP1</span><span class="sxs-lookup"><span data-stu-id="b683d-193">Step 2: Configure APP1</span></span>

<span data-ttu-id="b683d-194">在这一步，创建和配置 APP1，这是初始提供 Web 和文件共享服务的应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="b683d-194">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="b683d-195">若要为 APP1 创建 Azure 虚拟机，请填写资源组名称，并在本地计算机上的命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="b683d-195">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="b683d-196">接下来，使用 APP1 本地管理员帐户名称和密码连接到 APP1 虚拟机，然后打开 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="b683d-196">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="b683d-197">若要检查 APP1 和 DC1 之间的名称解析和网络通信，请运行 **ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="b683d-197">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="b683d-198">命令，并验证是否存在四个答复。</span><span class="sxs-lookup"><span data-stu-id="b683d-198">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="b683d-199">接下来，在 Windows PowerShell 提示符处，运行下面这些命令，将 APP1 虚拟机加入 TESTLAB 域。</span><span class="sxs-lookup"><span data-stu-id="b683d-199">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="b683d-200">请注意，在运行 " **外接程序** " 命令之后，必须提供 TESTLAB \\ User1 域帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="b683d-200">Note that you after you run the **Add-Computer** command, you must supply the TESTLAB\\User1 domain account credentials.</span></span>
  
<span data-ttu-id="b683d-201">在 APP1 重启后，使用 TESTLAB\\User1 帐户连接到它，再打开管理员级 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="b683d-201">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="b683d-202">接下来，在 APP1 上的管理员级 Windows PowerShell 命令提示符处，运行下面的命令，将 APP1 设置为 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="b683d-202">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="b683d-203">接下来，运行下面这些 PowerShell 命令，在 APP1 上的文件夹中创建共享文件夹和文本文件。</span><span class="sxs-lookup"><span data-stu-id="b683d-203">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="b683d-204">您的当前配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="b683d-204">Your current configuration looks like this:</span></span>
  
![模拟企业基础配置的步骤 2](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="b683d-206">步骤 3：配置 CLIENT1</span><span class="sxs-lookup"><span data-stu-id="b683d-206">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="b683d-207">在这一步，创建和配置 CLIENT1，这是 Intranet 上的典型笔记本电脑、平板电脑或台式计算机。</span><span class="sxs-lookup"><span data-stu-id="b683d-207">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="b683d-p122">下面的命令集会创建运行 Windows Server 2016 Datacenter 的 CLIENT1，可对所有类型的 Azure 订阅执行此操作。若有基于 Visual Studio 的 Azure 订阅，可通过 [Azure 门户](https://portal.azure.com)创建运行 Windows 10 的 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="b683d-p122">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span>
  
<span data-ttu-id="b683d-210">若要为 CLIENT1 创建 Azure 虚拟机，请填写资源组的名称，并在本地计算机上的命令提示符处运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="b683d-210">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="b683d-211">接下来，使用 CLIENT1 本地管理员帐户名称和密码连接到 CLIENT1 虚拟机，然后打开管理员级别 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="b683d-211">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="b683d-212">若要检查 CLIENT1 和 DC1 之间的名称解析和网络通信，请在 Windows PowerShell 命令提示符处运行 **ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="b683d-212">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="b683d-213">命令，并验证是否存在四个答复。</span><span class="sxs-lookup"><span data-stu-id="b683d-213">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="b683d-214">接下来，在 Windows PowerShell 提示符处，运行下面这些命令，将 CLIENT1 虚拟机加入 TESTLAB 域。</span><span class="sxs-lookup"><span data-stu-id="b683d-214">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="b683d-215">请注意，运行 **Add-Computer** 命令后，必须提供 TESTLAB\\User1 域帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="b683d-215">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="b683d-216">在 CLIENT1 重启后，使用 TESTLAB\\User1 帐户名和密码连接到它，再打开管理员级 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="b683d-216">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="b683d-217">接下来，验证能否从 CLIENT1 中的 APP1 访问 Web 和文件共享资源。</span><span class="sxs-lookup"><span data-stu-id="b683d-217">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="b683d-218">在服务器管理器的树窗格中，选择 " **本地服务器**"。</span><span class="sxs-lookup"><span data-stu-id="b683d-218">In Server Manager, in the tree pane, select **Local Server**.</span></span>
    
2. <span data-ttu-id="b683d-219">在 " **CLIENT1 的属性**" 中，选择 " **IE 增强的安全配置** **" 旁边的 "打开"** 。</span><span class="sxs-lookup"><span data-stu-id="b683d-219">In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="b683d-220">在 " **Internet Explorer 增强的安全配置**" 中，为**管理员**和**用户**选择 "**关闭**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b683d-220">In **Internet Explorer Enhanced Security Configuration**, select **Off** for **Administrators** and **Users**, and then select **OK**.</span></span>
    
4. <span data-ttu-id="b683d-221">在 "开始" 屏幕中，选择 " **Internet Explorer**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b683d-221">From the Start screen, select **Internet Explorer**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="b683d-222">在地址栏中，输入 " **http：<span>//</span>app1 testab** \<*your public domain name*> **/** "，然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="b683d-222">In the address bar, enter **http<span>://</span>app1.testab.**\<*your public domain name*>**/**, and then press **Enter**.</span></span> <span data-ttu-id="b683d-223">应该会看到 APP1 的默认 Internet Information Services 网页。</span><span class="sxs-lookup"><span data-stu-id="b683d-223">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="b683d-224">在桌面任务栏上，选择 "文件资源管理器" 图标。</span><span class="sxs-lookup"><span data-stu-id="b683d-224">On the desktop taskbar, select the File Explorer icon.</span></span>
    
7. <span data-ttu-id="b683d-225">在地址栏中，输入 " \*\* \\ \\ app1 \\ Files**"，然后按**enter\*\*。</span><span class="sxs-lookup"><span data-stu-id="b683d-225">In the address bar, enter **\\\\app1\\Files**, and then press **Enter**.</span></span> <span data-ttu-id="b683d-226">应该会看到带有文件共享文件夹内容的文件夹窗口。</span><span class="sxs-lookup"><span data-stu-id="b683d-226">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="b683d-p126">在“文件”\*\*\*\* 共享文件夹窗口中，双击“Example.txt”\*\*\*\* 文件。应该会看到 Example.txt 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="b683d-p126">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="b683d-229">关闭“example.txt - 记事本”\*\*\*\* 和“文件”\*\*\*\* 共享文件夹窗口。</span><span class="sxs-lookup"><span data-stu-id="b683d-229">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="b683d-230">您的当前配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="b683d-230">Your current configuration looks like this:</span></span>
  
![模拟企业基础配置的步骤 3](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="b683d-232">第 2 阶段：创建 Microsoft 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="b683d-232">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="b683d-p127">在此阶段，你将创建一个新的 Microsoft 365 E5 订阅，该订阅使用新的 Azure AD 租户（独立于生产订阅）。可通过两种方式实现此目的：</span><span class="sxs-lookup"><span data-stu-id="b683d-p127">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="b683d-235">使用 Microsoft 365 E5 的试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="b683d-235">Use a trial subscription of Microsoft 365 E5.</span></span>

  <span data-ttu-id="b683d-p128">Microsoft 365 E5 试用版订阅的有效期为 30 天，可轻松延长至 60 天。试用版订阅到期后，你必须将其转换为付费版订阅或创建新的试用版订阅。创建新的试用版订阅意味着你将保留配置，其中可能包含复杂的方案。</span><span class="sxs-lookup"><span data-stu-id="b683d-p128">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="b683d-239">使用包含少量许可证的 Microsoft 365 E5 独立生产订阅。</span><span class="sxs-lookup"><span data-stu-id="b683d-239">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="b683d-240">这是一种额外的成本，但可确保您的工作测试环境不会过期;在该示例中，您可以尝试功能、配置和方案。</span><span class="sxs-lookup"><span data-stu-id="b683d-240">This is an additional cost, but ensures that you have a working test environment that doesn't expire; in it, you can try features, configurations, and scenarios.</span></span> <span data-ttu-id="b683d-241">您可以对概念证明、对等项和管理的演示以及应用程序开发和测试使用长期的同一测试环境。</span><span class="sxs-lookup"><span data-stu-id="b683d-241">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="b683d-242">这是推荐使用的方法。</span><span class="sxs-lookup"><span data-stu-id="b683d-242">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="b683d-243">注册 Office 365 E5 试用订阅</span><span class="sxs-lookup"><span data-stu-id="b683d-243">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="b683d-244">在 Azure 门户中，使用 CORP\User1 帐户连接到 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="b683d-244">From the Azure portal, connect to CLIENT1 with the CORP\User1 account.</span></span>

<span data-ttu-id="b683d-245">若要创建新的 Office 365 E5 试用版订阅，请按照“轻型基准配置测试实验室指南”[阶段 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b683d-245">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="b683d-246">若要配置新的 Office 365 E5 试用版订阅，请按照“轻型基准配置测试实验室指南”[阶段 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b683d-246">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="b683d-247">使用 Office 365 E5 测试环境</span><span class="sxs-lookup"><span data-stu-id="b683d-247">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="b683d-248">如果只需要 Office 365 测试环境，则无需阅读本文的其余部分。</span><span class="sxs-lookup"><span data-stu-id="b683d-248">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="b683d-249">有关适用于 Microsoft 365 和 Office 365 的其他测试实验室指南，请参阅适用于 [企业测试实验室指南的 microsoft 365](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="b683d-249">For additional Test Lab Guides that apply to both Microsoft 365 and Office 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="b683d-250">添加 Microsoft 365 E5 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="b683d-250">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="b683d-251">若要添加 Microsoft 365 E5 试用订阅并使用许可证配置您的用户帐户，请按照轻型基本配置测试实验室指南的 [第3阶段](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b683d-251">To add a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="b683d-252">结果</span><span class="sxs-lookup"><span data-stu-id="b683d-252">Results</span></span>

<span data-ttu-id="b683d-253">测试环境现在包含：</span><span class="sxs-lookup"><span data-stu-id="b683d-253">Your test environment now has:</span></span>
  
- <span data-ttu-id="b683d-254">Microsoft 365 E5 试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="b683d-254">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="b683d-255">你所有相应的用户帐户都被允许使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="b683d-255">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="b683d-256">模拟和简化的 Intranet。</span><span class="sxs-lookup"><span data-stu-id="b683d-256">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="b683d-257">您的最终配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="b683d-257">Your final configuration looks like this:</span></span>
  
![模拟企业基础配置的第 2 阶段](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="b683d-259">现在，你可以试用 [Microsoft 365 for 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="b683d-259">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b683d-260">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b683d-260">Next steps</span></span>

<span data-ttu-id="b683d-261">浏览下面这些附加的一系列测试实验室指南：</span><span class="sxs-lookup"><span data-stu-id="b683d-261">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="b683d-262">标识</span><span class="sxs-lookup"><span data-stu-id="b683d-262">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="b683d-263">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="b683d-263">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="b683d-264">信息保护</span><span class="sxs-lookup"><span data-stu-id="b683d-264">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="b683d-265">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b683d-265">See also</span></span>

[<span data-ttu-id="b683d-266">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="b683d-266">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b683d-267">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="b683d-267">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b683d-268">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="b683d-268">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
