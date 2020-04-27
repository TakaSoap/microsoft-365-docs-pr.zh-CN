---
title: 用于 Microsoft 365 测试环境的联合身份
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 摘要：为 Microsoft 365 测试环境配置联合身份验证。
ms.openlocfilehash: b0aa967570c3d12554cdb273a8b39b8931af1fbd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634094"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="258c2-103">用于 Microsoft 365 测试环境的联合身份</span><span class="sxs-lookup"><span data-stu-id="258c2-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="258c2-104">*本测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="258c2-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="258c2-p101">Microsoft 365 支持联合标识。也就是说，Microsoft 365 将连接用户转到 Microsoft 365 信任的联合身份验证服务器，而不是自己执行凭据验证。如果用户的凭据正确，联合身份验证服务器会颁发安全令牌，然后客户端将此令牌作为通过身份验证的证明发送给 Microsofte 365。借助联合标识，可以为 Microsoft 365 订阅以及高级身份验证和安全方案卸载和扩展身份验证。</span><span class="sxs-lookup"><span data-stu-id="258c2-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="258c2-109">本文介绍了如何为 Microsoft 365 或 Office 365 测试环境配置联合身份验证，从而实现以下配置：</span><span class="sxs-lookup"><span data-stu-id="258c2-109">This article describes how you can configure federated authentication for your Microsoft 365 or Office 365 test environment, resulting in the following:</span></span>

![Microsoft 365 测试环境的联合身份验证](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="258c2-111">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="258c2-111">This configuration consists of:</span></span> 
  
- <span data-ttu-id="258c2-112">Microsoft 365 E5 或 Office 365 E5 试用版或生产订阅。</span><span class="sxs-lookup"><span data-stu-id="258c2-112">A Microsoft 365 E5 or Office 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="258c2-p102">连接 Internet 的简化组织 Intranet，由 Azure 虚拟网络子网中的五个虚拟机（DC1、APP1、CLIENT1、ADFS1 和 PROXY1）组成。Azure AD Connect 在 APP1 上运行，以便将 Active Directory 域服务域中的帐户列表同步到 Office 365。PROXY1 接收传入的身份验证请求。ADFS1 使用 DC1 验证凭据并颁发安全令牌。</span><span class="sxs-lookup"><span data-stu-id="258c2-p102">A simplified organization intranet connected to the Internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1). Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Office 365. PROXY1 receives the incoming authentication requests. ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="258c2-117">设置此测试环境分为五个阶段：</span><span class="sxs-lookup"><span data-stu-id="258c2-117">There are five phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="258c2-118">通过密码哈希同步创建模拟企业测试环境。</span><span class="sxs-lookup"><span data-stu-id="258c2-118">Create the simulated enterprise test environment with password hash synchronization.</span></span>
    
2. <span data-ttu-id="258c2-119">创建 AD FS 服务器 (ADFS1)。</span><span class="sxs-lookup"><span data-stu-id="258c2-119">Create the AD FS server (ADFS1).</span></span>
    
3. <span data-ttu-id="258c2-120">创建 Web 代理服务器 (PROXY1)。</span><span class="sxs-lookup"><span data-stu-id="258c2-120">Create the web proxy server (PROXY1).</span></span>
    
4. <span data-ttu-id="258c2-121">创建自签名证书并配置 ADFS1 和 PROXY1。</span><span class="sxs-lookup"><span data-stu-id="258c2-121">Create a self-signed certificate and configure ADFS1 and PROXY1.</span></span>
    
5. <span data-ttu-id="258c2-122">为 Microsoft 365 配置联合标识。</span><span class="sxs-lookup"><span data-stu-id="258c2-122">Configure Microsoft 365 for federated identity.</span></span>
    
> [!NOTE]
> <span data-ttu-id="258c2-123">无法使用 Azure 试用订阅配置此测试环境。</span><span class="sxs-lookup"><span data-stu-id="258c2-123">You cannot configure this test environment with an Azure Trial subscription.</span></span> 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="258c2-124">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="258c2-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="258c2-p103">按照 [Microsoft 365 的密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="258c2-p103">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="258c2-128">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="258c2-128">This configuration consists of:</span></span> 
  
- <span data-ttu-id="258c2-129">Microsoft 365 E5 或 Office 365 E5 试用版或付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="258c2-129">A Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="258c2-130">连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="258c2-130">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="258c2-131">在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB AD DS 域定期同步到 Microsoft 365 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="258c2-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="258c2-132">阶段 2：创建 AD FS 服务器</span><span class="sxs-lookup"><span data-stu-id="258c2-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="258c2-133">AD FS 服务器在 Microsoft 365 和 DC1 上托管的 corp.contoso.com 域中的帐户之间提供联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="258c2-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="258c2-134">若要为 ADFS1 创建 Azure 虚拟机，请填写基础配置的订阅和资源组名称及 Azure 位置，然后在本地计算机上的 Azure PowerShell 命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="258c2-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="258c2-135">接下来，通过 [Azure 门户](https://portal.azure.com)使用 ADFS1 本地管理员帐户名称和密码连接 ADFS1 虚拟机，然后打开 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="258c2-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="258c2-136">若要检查 ADFS1 和 DC1 之间的名称解析和网络通信，请运行 **ping dc1.corp.contoso.com** 命令，然后查看是否存在四个答复。</span><span class="sxs-lookup"><span data-stu-id="258c2-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="258c2-137">接下来，在 ADFS1 上的 Windows PowerShell 提示符处运行下面这些命令，将 ADFS1 虚拟机加入 CORP 域。</span><span class="sxs-lookup"><span data-stu-id="258c2-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="258c2-138">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="258c2-138">Here is your resulting configuration.</span></span>
  
![添加到用于 Microsoft 365 测试环境的 DirSync 的 AD FS 服务器](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="258c2-140">阶段 3：创建 Web 代理服务器</span><span class="sxs-lookup"><span data-stu-id="258c2-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="258c2-141">PROXY1 在尝试进行身份验证的用户和 ADFS1 之间提供身份验证消息代理。</span><span class="sxs-lookup"><span data-stu-id="258c2-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="258c2-142">若要为 PROXY1 创建 Azure 虚拟机，请填写资源组名称和 Azure 位置，然后在本地计算机上的 Azure PowerShell 命令提示符处运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="258c2-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="258c2-143">PROXY1 分配有一个静态公共 IP 地址，因为将创建一个指向它的公共 DNS 记录，并且它不得在 PROXY1 虚拟机重启时有变化。</span><span class="sxs-lookup"><span data-stu-id="258c2-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span> 
  
<span data-ttu-id="258c2-p105">接下来，将规则添加到 CorpNet 子网的网络安全组中，以允许来自 Internet 未经请求的入站流量流入 PROXY1 的专用 IP 地址和 TCP 端口 443。在本地计算机上的 Azure PowerShell 命令提示符处，运行下面这些命令。</span><span class="sxs-lookup"><span data-stu-id="258c2-p105">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the Internet to PROXY1's private IP address and TCP port 443. Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="258c2-146">接下来，通过 [Azure 门户](https://portal.azure.com)，使用 PROXY1 本地管理员帐户名称和密码连接 PROXY1 虚拟机，然后在 PROXY1 上打开 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="258c2-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="258c2-147">若要检查 PROXY1 和 DC1 之间的名称解析和网络通信，请运行 **ping dc1.corp.contoso.com** 命令，然后查看是否存在四个答复。</span><span class="sxs-lookup"><span data-stu-id="258c2-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="258c2-148">接下来，在 PROXY1 上的 Windows PowerShell 提示符处运行下面这些命令，将 PROXY1 虚拟机加入 CORP 域。</span><span class="sxs-lookup"><span data-stu-id="258c2-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="258c2-149">在本地计算机上运行以下 Azure PowerShell 命令，显示 PROXY1 的公共 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="258c2-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="258c2-p106">接下来，结合使用公共 DNS 提供程序，为解析为 **Write-Host** 命令显示的 IP 地址的 **fs.testlab.**\<DNS 域名> 新建一个公共 DNS A 记录。**fs.testlab.**\<DNS 域名> 以下称为*联合身份验证服务 FQDN*。</span><span class="sxs-lookup"><span data-stu-id="258c2-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<your DNS domain name> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<your DNS domain name> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="258c2-152">接下来，通过 [Azure 门户](https://portal.azure.com)，使用 CORP\\User1 凭据连接 DC1 虚拟机，然后在管理员级 Windows PowerShell 命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="258c2-152">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="258c2-153">这些命令会创建内部 DNS A 记录，这样 Azure 虚拟网络上的虚拟机便可将内部联合身份验证 FQDN 解析为 ADFS1 的专用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="258c2-153">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="258c2-154">下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="258c2-154">Here is your resulting configuration.</span></span>
  
![添加到用于 Microsoft 365 测试环境的 DirSync 的 Web 应用程序代理服务器](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="258c2-156">阶段 4：创建自签名证书并配置 ADFS1 和 PROXY1</span><span class="sxs-lookup"><span data-stu-id="258c2-156">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="258c2-157">在此阶段，将为联合身份验证服务 FQDN 创建自签名数字证书，并将 ADFS1 和 PROXY1 配置为 AD FS 场。</span><span class="sxs-lookup"><span data-stu-id="258c2-157">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="258c2-158">首先，通过 [Azure 门户](https://portal.azure.com)，使用 CORP\\User1 凭据连接 DC1 虚拟机，然后打开管理员级 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="258c2-158">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="258c2-159">接下来，在 DC1 上的 Windows PowerShell 命令提示符处运行以下命令，创建 AD FS 服务帐户：</span><span class="sxs-lookup"><span data-stu-id="258c2-159">Next, create AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="258c2-p107">请注意，此命令会提示你提供帐户密码。选择强密码，然后在安全位置记录此密码。此阶段和阶段 5 都要用到它。</span><span class="sxs-lookup"><span data-stu-id="258c2-p107">Note that this command prompts you to supply the account password. Choose a strong password and record it in a secured location. You will need it for this phase and Phase 5.</span></span>
  
<span data-ttu-id="258c2-p108">通过 [Azure 门户](https://portal.azure.com)，使用 CORP\\User1 凭据连接 ADFS1 虚拟机。在 ADFS1 上打开管理员级 Windows PowerShell 命令提示符，填写联合身份验证服务 FQDN，然后运行下面这些命令，从而创建自签名证书：</span><span class="sxs-lookup"><span data-stu-id="258c2-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="258c2-165">接下来，按下面这些步骤操作，将新建的自签名证书保存为文件。</span><span class="sxs-lookup"><span data-stu-id="258c2-165">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="258c2-166">单击“开始”，键入“mmc.exe”，然后按 Enter 键。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-166">Click **Start**, type **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="258c2-167">依次单击“文件”>“添加/删除管理单元”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-167">Click **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="258c2-168">在“添加或删除管理单元”中，双击可用管理单元列表中的“证书”，然后依次单击“计算机帐户”和“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-168">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, click **Computer account**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="258c2-169">在“选择计算机”中，依次单击“完成”和“确定”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-169">In **Select Computer**, click **Finish**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="258c2-170">在树窗格中，依次打开“证书(本地计算机)”>“个人”>“证书”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-170">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="258c2-171">右键单击包含联合身份验证服务 FQDN 的证书，然后依次单击“所有任务”和“导出”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-171">Right-click the certificate with your federation service FQDN, click **All tasks**, and then click **Export**.</span></span>
    
7. <span data-ttu-id="258c2-172">在“欢迎”页上，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="258c2-172">On the **Welcome** page, click **Next**.</span></span>
    
8. <span data-ttu-id="258c2-173">在“导出私钥”页上，依次单击“是”和“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-173">On the **Export Private Key** page, click **Yes**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="258c2-174">在“导出文件格式”页上，依次单击“导出所有扩展属性”和“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-174">On the **Export File Format** page, click **Export all extended properties**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="258c2-175">在“安全性”页上，单击“密码”，然后在“密码”和“确认密码”中键入密码。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-175">On the **Security** page, click **Password** and type a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="258c2-176">在“要导出的文件”页上，单击“浏览”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-176">On the **File to Export** page, click **Browse**.</span></span>
    
12. <span data-ttu-id="258c2-177">浏览至“C:\\Certs”文件夹，在“文件名”中键入“SSL”，然后单击“保存”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-177">Browse to the **C:\\Certs** folder, type **SSL** in **File name**, and then click **Save.**</span></span>
    
13. <span data-ttu-id="258c2-178">在“要导出的文件”页上，单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-178">On the **File to Export** page, click **Next**.</span></span>
    
14. <span data-ttu-id="258c2-p109">在“正在完成证书导出向导”页上，单击“完成”。当出现提示时，单击“确定”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-p109">On the **Completing the Certificate Export Wizard** page, click **Finish**. When prompted, click **OK**.</span></span>
    
<span data-ttu-id="258c2-181">接下来，在 ADFS1 上的 Windows PowerShell 命令提示符处运行以下命令，安装 AD FS 服务：</span><span class="sxs-lookup"><span data-stu-id="258c2-181">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="258c2-182">等待安装完成。</span><span class="sxs-lookup"><span data-stu-id="258c2-182">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="258c2-183">接下来，按下面这些步骤操作，配置 AD FS 服务：</span><span class="sxs-lookup"><span data-stu-id="258c2-183">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="258c2-184">依次单击“开始”和“服务器管理器”图标。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-184">Click **Start**, and then click the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="258c2-185">在“服务器管理器”树窗格中，单击“AD FS”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-185">In the tree pane of Server Manager, click **AD FS**.</span></span>
    
3. <span data-ttu-id="258c2-186">在顶部工具栏中，依次单击橙色警告符号和“在此服务器上配置联合身份验证服务”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-186">In the tool bar at the top, click the orange caution symbol, and then click **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="258c2-187">在“Active Directory 联合身份验证服务配置向导”的“欢迎”页上，单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-187">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, click **Next**.</span></span>
    
5. <span data-ttu-id="258c2-188">在“连接到 AD DS”页上，单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-188">On the **Connect to AD DS** page, click **Next**.</span></span>
    
6. <span data-ttu-id="258c2-189">在“指定服务属性”页上：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-189">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="258c2-190">对于“SSL 证书”，依次单击向下箭头和包含联合身份验证服务 FQDN 名称的证书。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-190">For **SSL Certificate**, click the down arrow, and then click the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="258c2-191">在“联合身份验证服务显示名称”中，键入虚构组织的名称。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-191">In **Federation Service Display Name**, type the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="258c2-192">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-192">Click **Next**.</span></span>
    
7. <span data-ttu-id="258c2-193">在“指定服务帐户”页上，单击“选择”来选择“帐户名称”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-193">On the **Specify Service Account** page, click **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="258c2-194">在“选择用户或服务帐户”中，键入“ADFS-Service”，然后依次单击“检查名称”和“确定”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-194">In **Select User or Service Account**, type **ADFS-Service**, click **Check Names**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="258c2-195">在“帐户密码”中，键入 ADFS-Service 帐户密码，然后单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-195">In **Account Password**, type the password for the ADFS-Service account, and then click **Next**.</span></span>
    
10. <span data-ttu-id="258c2-196">在“指定配置数据库”页上，单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-196">On the **Specify Configuration Database** page, click **Next**.</span></span>
    
11. <span data-ttu-id="258c2-197">在“查看选项”页上，单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-197">On the **Review Options** page, click **Next**.</span></span>
    
12. <span data-ttu-id="258c2-198">在“先决条件检查”页上，单击“配置”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-198">On the **Pre-requisite Checks** page, click **Configure**.</span></span>
    
13. <span data-ttu-id="258c2-199">在“结果”页上，单击“关闭”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-199">On the **Results** page, click **Close**.</span></span>
    
14. <span data-ttu-id="258c2-200">依次单击“开始”、电源图标、“重启”和“继续”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-200">Click **Start**, click the power icon, click **Restart**, and then click **Continue**.</span></span>
    
<span data-ttu-id="258c2-201">通过 CORP\\User1 帐户凭据从 [Azure 门户](https://portal.azure.com)连接到 PROXY1。</span><span class="sxs-lookup"><span data-stu-id="258c2-201">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="258c2-202">接下来，按下面这些步骤操作，安装自签名证书并配置 PROXY1。</span><span class="sxs-lookup"><span data-stu-id="258c2-202">Next, use these steps to install the self-signed certificate and configure PROXY1.</span></span>
  
1. <span data-ttu-id="258c2-203">单击“开始”，键入“mmc.exe”，然后按 Enter 键。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-203">Click **Start**, type **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="258c2-204">依次单击“文件”>“添加/删除管理单元”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-204">Click **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="258c2-205">在“添加或删除管理单元”中，双击可用管理单元列表中的“证书”，然后依次单击“计算机帐户”和“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-205">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, click **Computer account**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="258c2-206">在“选择计算机”中，依次单击“完成”和“确定”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-206">In **Select Computer**, click **Finish**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="258c2-207">在树窗格中，依次打开“证书(本地计算机)”>“个人”>“证书”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-207">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="258c2-208">右键单击“个人”，然后依次单击“所有任务”和“导入”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-208">Right-click **Personal**, click **All tasks**, and then click **Import**.</span></span>
    
7. <span data-ttu-id="258c2-209">在“欢迎”页上，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="258c2-209">On the **Welcome** page, click **Next**.</span></span>
    
8. <span data-ttu-id="258c2-210">在“要导入的文件”页上，键入“**\\\\adfs1\\certs\\ssl.pfx**”，然后单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-210">On the **File to Import** page, type **\\\\adfs1\\certs\\ssl.pfx**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="258c2-211">在“私钥保护”页上的“密码”中键入证书密码，然后单击“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-211">On the **Private key protection** page, type the certificate password in **Password**, and then click **Next.**</span></span>
    
10. <span data-ttu-id="258c2-212">在“证书存储”页上，单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-212">On the **Certificate store** page, click **Next.**</span></span>
    
11. <span data-ttu-id="258c2-213">在“正在完成”页上，单击“完成”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-213">On the **Completing** page, click **Finish**.</span></span>
    
12. <span data-ttu-id="258c2-214">在“证书存储”页上，单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-214">On the **Certificate Store** page, click **Next**.</span></span>
    
13. <span data-ttu-id="258c2-215">当出现提示时，单击“确定”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-215">When prompted, click **OK**.</span></span>
    
14. <span data-ttu-id="258c2-216">单击树窗格中“证书”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-216">Click **Certificates** in the tree pane.</span></span>
    
15. <span data-ttu-id="258c2-217">右键单击证书，然后单击“复制”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-217">Right-click the certificate, and then click **Copy**.</span></span>
    
16. <span data-ttu-id="258c2-218">在树窗格中，依次打开“受信任的根证书颁发机构”>“证书”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-218">In the tree pane, open **Trusted Root Certification Authorities > Certificates**.</span></span>
    
17. <span data-ttu-id="258c2-219">将鼠标指针移到已安装证书列表下方，右键单击，然后单击“粘贴”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-219">Move your mouse pointer below the list of installed certificates, right-click, and then click **Paste**.</span></span>
    
<span data-ttu-id="258c2-220">打开管理员级 PowerShell 命令提示符，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="258c2-220">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="258c2-221">等待安装完成。</span><span class="sxs-lookup"><span data-stu-id="258c2-221">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="258c2-222">按下面这些步骤操作，将 Web 应用程序代理服务配置为使用 ADFS1 作为其联合服务器：</span><span class="sxs-lookup"><span data-stu-id="258c2-222">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="258c2-223">单击“开始”，再单击“服务器管理器”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-223">Click **Start**, and then click **Server Manager**.</span></span>
    
2. <span data-ttu-id="258c2-224">在树窗格中，单击“远程访问”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-224">In the tree pane, click **Remote Access**.</span></span>
    
3. <span data-ttu-id="258c2-225">在顶部工具栏中，依次单击橙色警告符号和“打开‘Web 应用程序代理向导’”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-225">In the tool bar at the top, click the orange caution symbol, and then click **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="258c2-226">在“Web 应用程序代理配置向导”的“欢迎”页上，单击“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-226">On the **Welcome** page of the Web Application Proxy Configuration Wizard, click **Next**.</span></span>
    
5. <span data-ttu-id="258c2-227">在“联合服务器”页上：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-227">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="258c2-228">在“联合身份验证服务名称”中，键入联合身份验证服务 FQDN。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-228">Type your federation service FQDN in **Federation service name**.</span></span>
    
  - <span data-ttu-id="258c2-229">在“用户名”中，键入“CORP\\User1”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-229">Type **CORP\\User1** in **User name**.</span></span>
    
  - <span data-ttu-id="258c2-230">在“密码”中，键入 User1 帐户密码。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-230">Type the password for the User1 account in **Password**.</span></span>
    
  - <span data-ttu-id="258c2-231">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-231">Click **Next**.</span></span>
    
6. <span data-ttu-id="258c2-232">在“AD FS 代理证书”页上，依次单击向下箭头、包含联合身份验证服务 FQDN 的证书和“下一步”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-232">On the **AD FS Proxy Certificate** page, click the down arrow, click the certificate with your federation service FQDN, and then click **Next**.</span></span>
    
7. <span data-ttu-id="258c2-233">在“确认”页上，单击“配置”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-233">On the **Confirmation** page, click **Configure**.</span></span>
    
8. <span data-ttu-id="258c2-234">在“结果”页上，单击“关闭”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-234">On the **Results** page, click **Close**.</span></span>

    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="258c2-235">第 5 阶段：为 Microsoft 365 配置联合标识。</span><span class="sxs-lookup"><span data-stu-id="258c2-235">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="258c2-236">通过 [Azure 门户](https://portal.azure.com)，使用 CORP\\User1 帐户凭据连接 APP1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="258c2-236">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="258c2-237">若要为 Azure AD Connect 和 Microsoft 365 订阅配置联合身份验证，请按照下面这些步骤操作：</span><span class="sxs-lookup"><span data-stu-id="258c2-237">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="258c2-238">在桌面上，双击“Azure AD Connect”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="258c2-238">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="258c2-239">在“欢迎使用 Azure AD Connect”页上，单击“配置”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-239">On the **Welcome to Azure AD Connect** page, click **Configure**.</span></span>
    
3. <span data-ttu-id="258c2-240">在“其他任务”页上，依次单击“更改用户登录”和“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-240">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="258c2-241">在“连接到 Azure AD”\*\*\*\* 页上，键入全局管理员帐户名和密码，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="258c2-241">On the **Connect to Azure AD** page, type your global administrator account name and password, and then click **Next**.</span></span>
    
5. <span data-ttu-id="258c2-242">在“用户登录”页上，依次单击“使用 AD FS 进行联合身份验证”和“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-242">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="258c2-243">在“AD FS 场”页上，单击“使用现有 AD FS 场”，在“服务器名称”中键入“ADFS1”，然后单击“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-243">On the **AD FS farm** page, click **Use an existing AD FS farm**, type **ADFS1** in **Server Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="258c2-244">当系统提示输入服务器凭据时，输入 CORP\\User1 帐户凭据，然后单击“确定”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-244">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then click **OK**.</span></span>
    
8. <span data-ttu-id="258c2-245">在“域管理员”凭据页上，在“用户名”中键入“CORP\\User1”，在“密码”中键入帐户密码，然后单击“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-245">On the **Domain Administrator** credentials page, type **CORP\\User1** in **Username** and the account password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="258c2-246">在“AD FS 服务帐户”页上，在“域用户名”中键入“CORP\\ADFS-Service”，在“域用户密码”中键入帐户密码，然后单击“下一步”。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-246">On the **AD FS service account** page, type **CORP\\ADFS-Service** in **Domain Username** and the account password in **Domain User Password**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="258c2-247">在“Azure AD 域”\*\*\*\* 页上的“域”\*\*\*\* 中，选择之前在第 1 阶段中创建并添加到订阅的域名，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="258c2-247">On the **Azure AD Domain** page, in **Domain**, select the name of the domain you previously created and added to your subscription in Phase 1, and then click **Next**.</span></span>
    
11. <span data-ttu-id="258c2-248">在“**准备配置**”页面上，单击“**配置**”。</span><span class="sxs-lookup"><span data-stu-id="258c2-248">On the **Ready to configure** page, click **Configure**.</span></span>
    
12. <span data-ttu-id="258c2-249">在“安装完成”页上，单击“验证”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-249">On the **Installation complete** page, click **Verify**.</span></span>
    
    <span data-ttu-id="258c2-250">应该可以看到指明 Intranet 和 Internet 配置均已验证的消息。</span><span class="sxs-lookup"><span data-stu-id="258c2-250">You should see messages indicating that both the intranet and Internet configuration was verified.</span></span>
    
13. <span data-ttu-id="258c2-251">在“安装完成”页上，单击“退出”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-251">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="258c2-252">若要证明联合身份验证能够正常运行，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="258c2-252">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="258c2-253">在本地计算机上打开浏览器的新专用实例，然后转到 [https://admin.microsoft.com](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="258c2-253">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="258c2-254">对于登录凭据，请键入 **user1@**\<在阶段 1 创建的域>。</span><span class="sxs-lookup"><span data-stu-id="258c2-254">For the sign-in credentials, type **user1@**\<the domain created in Phase 1>.</span></span> 
    
    <span data-ttu-id="258c2-p110">例如，如果测试域是 **testlab.contoso.com**，你会键入“user1@testlab.contoso.com”。按 TAB 或允许 Microsoft 365 自动重定向你。</span><span class="sxs-lookup"><span data-stu-id="258c2-p110">For example, if your test domain is **testlab.contoso.com**, you would type "user1@testlab.contoso.com". Press TAB or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="258c2-p111">现在应该可以看到“**你所用连接不是专用连接**”页。之所以会看到此页是因为你在 ADFS1 上安装了台式计算机无法验证的自签名证书。在联合身份验证的生产部署中，将使用受信任的证书颁发机构颁发的证书，你的用户将不会看到此页。</span><span class="sxs-lookup"><span data-stu-id="258c2-p111">You should now see a **Your connection is not private** page. You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer cannot validate. In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="258c2-260">在“你所用连接不是专用连接”页上，依次单击“高级”和“继续处理 \<联合身份验证服务 FQDN>”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-260">On the **Your connection is not private** page, click **Advanced**, and then click **Proceed to \<your federation service FQDN>**.</span></span> 
    
4. <span data-ttu-id="258c2-261">在包含虚构组织名称的页上，使用以下凭据登录：</span><span class="sxs-lookup"><span data-stu-id="258c2-261">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="258c2-262">该名称的 **CORP\\User1**</span><span class="sxs-lookup"><span data-stu-id="258c2-262">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="258c2-263">User1 帐户密码</span><span class="sxs-lookup"><span data-stu-id="258c2-263">The password for the User1 account</span></span>
    
    <span data-ttu-id="258c2-264">应该会看到“Microsoft Office 主页”页面。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="258c2-264">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="258c2-p112">此过程证明了试用订阅与 DC1 上托管的 AD DS corp.contoso.com 域进行了联合。下面是身份验证流程的基本信息：</span><span class="sxs-lookup"><span data-stu-id="258c2-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="258c2-267">如果你在登录帐户名中使用在第 1 阶段中创建的联盟域，Microsoft 365 将浏览器重定向到联合身份验证服务 FQDN 和 PROXY1。</span><span class="sxs-lookup"><span data-stu-id="258c2-267">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="258c2-268">PROXY1 向本地计算机发送虚构的公司登录页。</span><span class="sxs-lookup"><span data-stu-id="258c2-268">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="258c2-269">PROXY1 会将你发送给它的 CORP\\User1 和密码转发给 ADFS1。</span><span class="sxs-lookup"><span data-stu-id="258c2-269">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="258c2-270">ADFS1 使用 DC1 验证 CORP\\User1 和密码，然后向本地计算机发送安全令牌。</span><span class="sxs-lookup"><span data-stu-id="258c2-270">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="258c2-271">本地计算机向 Microsoft 365 发送安全令牌。</span><span class="sxs-lookup"><span data-stu-id="258c2-271">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="258c2-272">Microsoft 365 验证安全令牌是否由 ADFS1 创建，并在验证通过后允许访问。</span><span class="sxs-lookup"><span data-stu-id="258c2-272">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="258c2-p113">现在，试用订阅已配置了联合身份验证。可以将此开发/测试环境用于高级身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="258c2-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="258c2-275">后续步骤</span><span class="sxs-lookup"><span data-stu-id="258c2-275">Next step</span></span>

<span data-ttu-id="258c2-276">如果准备好在 Azure 中为 Microsoft 365 或 Office 365 部署生产就绪、高可用性联合身份验证，请参阅[在 Azure 中为 Microsoft 365 部署高可用性联合身份验证](https://docs.microsoft.com/office365/enterprise/deploy-high-availability-federated-authentication-for-office-365-in-azure)。</span><span class="sxs-lookup"><span data-stu-id="258c2-276">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 or Office 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](https://docs.microsoft.com/office365/enterprise/deploy-high-availability-federated-authentication-for-office-365-in-azure).</span></span>
  
