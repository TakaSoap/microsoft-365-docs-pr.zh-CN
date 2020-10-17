---
title: 用于 Microsoft 365 测试环境的联合身份
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
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
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487680"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>用于 Microsoft 365 测试环境的联合身份

*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*

Microsoft 365 支持联合标识。也就是说，Microsoft 365 将连接用户转到 Microsoft 365 信任的联合身份验证服务器，而不是自己执行凭据验证。如果用户的凭据正确，联合身份验证服务器会颁发安全令牌，然后客户端将此令牌作为通过身份验证的证明发送给 Microsofte 365。借助联合标识，可以为 Microsoft 365 订阅以及高级身份验证和安全方案卸载和扩展身份验证。
  
本文介绍如何为 Microsoft 365 测试环境配置联合身份验证，从而产生以下结果：

![Microsoft 365 测试环境的联合身份验证](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
此配置包括：
  
- Microsoft 365 E5 试用版或生产版订阅。
    
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的五个虚拟机组成 (DC1、APP1、CLIENT1、ADFS1 和 PROXY1) 。 Azure AD Connect 在 APP1 上运行，以将 Active Directory 域服务域中的帐户列表与 Microsoft 365 同步。 PROXY1 接收传入的身份验证请求。 ADFS1 使用 DC1 验证凭据并颁发安全令牌。
    
设置此测试环境涉及五个阶段：
- [阶段 1：为 Microsoft 365 测试环境配置密码哈希同步](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [阶段 2：创建 AD FS 服务器](#phase-2-create-the-ad-fs-server)
- [阶段 3：创建 Web 代理服务器](#phase-3-create-the-web-proxy-server)
- [阶段 4：创建自签名证书并配置 ADFS1 和 PROXY1](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [第 5 阶段：为 Microsoft 365 配置联合标识。](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> 无法使用 Azure 试用订阅配置此测试环境。
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>阶段 1：为 Microsoft 365 测试环境配置密码哈希同步

按照 [针对 Microsoft 365 的密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明进行操作。 生成的配置如下所示：
  
![使用密码哈希同步测试环境的模拟企业配置](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
此配置包括：
  
- Microsoft 365 E5 试用版或付费版订阅。
- 连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。 Azure AD Connect 在 APP1 上运行，以将 AD DS) 域的 TESTLAB Active Directory 域服务 (为定期向 Microsoft 365 订阅的 Azure AD 租户进行同步。

## <a name="phase-2-create-the-ad-fs-server"></a>阶段 2：创建 AD FS 服务器

AD FS 服务器在 Microsoft 365 和 DC1 上托管的 corp.contoso.com 域中的帐户之间提供联合身份验证。
  
若要为 ADFS1 创建 Azure 虚拟机，请填写基础配置的订阅和资源组名称及 Azure 位置，然后在本地计算机上的 Azure PowerShell 命令提示符处运行下面这些命令。
  
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

接下来，通过 [Azure 门户](https://portal.azure.com)使用 ADFS1 本地管理员帐户名称和密码连接 ADFS1 虚拟机，然后打开 Windows PowerShell 命令提示符。
  
若要检查 ADFS1 和 DC1 之间的名称解析和网络通信，请运行 **ping dc1.corp.contoso.com** 命令，然后查看是否存在四个答复。
  
接下来，在 ADFS1 上的 Windows PowerShell 提示符处运行下面这些命令，将 ADFS1 虚拟机加入 CORP 域。
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

生成的配置如下所示：
  
![添加到用于 Microsoft 365 测试环境的 DirSync 的 AD FS 服务器](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>阶段 3：创建 Web 代理服务器

PROXY1 在尝试进行身份验证的用户和 ADFS1 之间提供身份验证消息代理。
  
若要为 PROXY1 创建 Azure 虚拟机，请填写资源组名称和 Azure 位置，然后在本地计算机上的 Azure PowerShell 命令提示符处运行下面这些命令。
  
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
> PROXY1 分配有一个静态公共 IP 地址，因为将创建一个指向它的公共 DNS 记录，并且它不得在 PROXY1 虚拟机重启时有变化。
  
接下来，将规则添加到企业网络子网的网络安全组，以允许来自 internet 的未经请求的入站流量从 internet 到 PROXY1's 的专用 IP 地址和 TCP 端口443。 在本地计算机上的 Azure PowerShell 命令提示符处，运行下面这些命令。
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

接下来，通过 [Azure 门户](https://portal.azure.com)，使用 PROXY1 本地管理员帐户名称和密码连接 PROXY1 虚拟机，然后在 PROXY1 上打开 Windows PowerShell 命令提示符。
  
若要检查 PROXY1 和 DC1 之间的名称解析和网络通信，请运行 **ping dc1.corp.contoso.com** 命令，然后查看是否存在四个答复。
  
接下来，在 PROXY1 上的 Windows PowerShell 提示符处运行下面这些命令，将 PROXY1 虚拟机加入 CORP 域。
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

在本地计算机上使用这些 Azure PowerShell 命令显示 PROXY1 的公共 IP 地址。
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

接下来，结合使用公共 DNS 提供程序，为解析为由 **Write-Host** 命令显示的 IP 地址的 **fs.testlab.**\<*your DNS domain name*> 新建一个公共 DNS A 记录。**fs.testlab.**\<*your DNS domain name*> 以下称为*联合身份验证服务 FQDN*。
  
接下来，通过 [Azure 门户](https://portal.azure.com)，使用 CORP\\User1 凭据连接 DC1 虚拟机，然后在管理员级 Windows PowerShell 命令提示符处运行以下命令：
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
这些命令创建内部 DNS A 记录，以便 Azure 虚拟网络上的虚拟机可以将内部联合身份验证服务 FQDN 解析为 ADFS1's 专用 IP 地址。
  
生成的配置如下所示：
  
![添加到用于 Microsoft 365 测试环境的 DirSync 的 Web 应用程序代理服务器](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>阶段 4：创建自签名证书并配置 ADFS1 和 PROXY1

在此阶段，将为联合身份验证服务 FQDN 创建自签名数字证书，并将 ADFS1 和 PROXY1 配置为 AD FS 场。
  
首先，通过 [Azure 门户](https://portal.azure.com)，使用 CORP\\User1 凭据连接 DC1 虚拟机，然后打开管理员级 Windows PowerShell 命令提示符。
  
接下来，在 DC1 上的 Windows PowerShell 命令提示符处，使用以下命令创建 AD FS 服务帐户：
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
请注意，此命令会提示你提供帐户密码。 选择强密码，然后在安全位置记录此密码。 在此阶段和第5阶段将需要它。
  
通过 [Azure 门户](https://portal.azure.com)，使用 CORP\\User1 凭据连接 ADFS1 虚拟机。在 ADFS1 上打开管理员级 Windows PowerShell 命令提示符，填写联合身份验证服务 FQDN，然后运行下面这些命令，从而创建自签名证书：
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

接下来，按下面这些步骤操作，将新建的自签名证书保存为文件。
  
1. 选择 " **开始**"，输入 **mmc.exe**，然后按 **enter**。
    
2. 选择 "**文件**" "  >  **添加/删除管理单元"**。
    
3. 在 " **添加或删除管理单元**" 中，双击可用管理单元列表中的 " **证书** "，选择 " **计算机帐户**"，然后选择 " **下一步**"。
    
4. 在 " **选择计算机**" 中，选择 " **完成**"，然后选择 **"确定"**。
    
5. 在树窗格中，依次打开“证书(本地计算机)”>“个人”>“证书”。****
    
6. 选择并按住 (，或右键单击) 使用联合身份验证服务 FQDN 的证书，选择 " **所有任务**"，然后选择 " **导出**"。
    
7. 在 " **欢迎** " 页上，选择 " **下一步**"。
    
8. 在 " **导出私钥** " 页上，选择 **"是**"，然后选择 " **下一步**"。
    
9. 在 " **导出文件格式** " 页上，选择 " **导出所有扩展属性**"，然后选择 " **下一步**"。
    
10. 在 "**安全**" 页上，选择 "**密码**"，并在 "**密码**" 和 "**确认密码**" 中输入密码。
    
11. 在 " **要导出的文件** " 页上，选择 " **浏览**"。
    
12. 浏览到 " **C： \\ 证书**" 文件夹，在 "**文件名**" 中输入**SSL** ，然后选择 "**保存"。**
    
13. 在 " **要导出的文件** " 页上，选择 " **下一步**"。
    
14. 在 " **正在完成证书导出向导** " 页上，选择 " **完成**"。 出现提示时，选择 **"确定"**。
    
接下来，在 ADFS1 上的 Windows PowerShell 命令提示符处运行以下命令，安装 AD FS 服务：
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

等待安装完成。
  
接下来，按下面这些步骤操作，配置 AD FS 服务：
  
1. 选择 " **开始**"，然后选择 " **服务器管理器** " 图标。
    
2. 在服务器管理器的树窗格中，选择 " **AD FS**"。
    
3. 在顶部的工具栏中，选择橙色警告符号，然后选择 " **在此服务器上配置联合身份验证服务**"。
    
4. 在 "Active Directory 联合身份验证服务配置向导" 的 " **欢迎** " 页上，选择 " **下一步**"。
    
5. 在 " **连接到 AD DS** " 页上，选择 " **下一步**"。
    
6. 在“指定服务属性”页上：****
    
  - 对于 " **SSL 证书**"，选择向下箭头，然后选择 "证书"，其中包含联合身份验证服务 FQDN 的名称。
    
  - 在 " **联合身份验证服务显示名称**" 中，输入虚构组织的名称。
    
  - 选择“**下一步**”。
    
7. 在 "**指定服务帐户**" 页上，选择 "为**帐户名称****选择**"。
    
8. 在 " **选择用户或服务帐户**" 中，输入 " **ADFS-服务**"，选择 " **检查名称**"，然后选择 **"确定"**。
    
9. 在 " **帐户密码**" 中，输入 ADFS-Service 帐户的密码，然后选择 " **下一步**"。
    
10. 在 " **指定配置数据库** " 页上，选择 " **下一步**"。
    
11. 在 " **查看选项** " 页上，选择 " **下一步**"。
    
12. 在 " **先决条件检查** " 页上，选择 " **配置**"。

13. 在 " **结果** " 页上，选择 " **关闭**"。
    
14. 选择 " **开始**"，选择 "电源" 图标，选择 " **重新启动**"，然后选择 " **继续**"。
    
通过 CORP\\User1 帐户凭据从 [Azure 门户](https://portal.azure.com)连接到 PROXY1。
  
接下来，按下面这些步骤操作，在 **PROXY1 和 APP1** 上安装自签名证书。
  
1. 选择 " **开始**"，输入 **mmc.exe**，然后按 **enter**。
    
2. 选择 " **文件" > "添加/删除管理单元"**。
    
3. 在 " **添加或删除管理单元**" 中，双击可用管理单元列表中的 " **证书** "，选择 " **计算机帐户**"，然后选择 " **下一步**"。
    
4. 在 " **选择计算机**" 中，选择 " **完成**"，然后选择 **"确定"**。
    
5. 在树窗格中，打开 " ** (本地计算机) **  >  **个人**  >  **证书**" 的 "证书"。
    
6. 选择并按住 (，或右键单击) **个人**"，选择" **所有任务**"，然后选择" **导入**"。
    
7. 在 " **欢迎** " 页上，选择 " **下一步**"。
    
8. 在 "**要导入的文件**" 页上，输入** \\ \\ adfs1 \\ 证书 \\ ssl .pfx**，然后选择 "**下一步**"。
    
9. 在 " **私钥保护** " 页上，在 " **密码**" 中输入证书密码，然后选择 " **下一步"。**
    
10. 在 " **证书存储** " 页上，选择 " **下一步"。**
    
11. 在 " **完成** " 页上，选择 " **完成**"。
    
12. 在 " **证书存储** " 页上，选择 " **下一步**"。
    
13. 出现提示时，选择 **"确定"**。
    
14. 在树窗格中，选择 " **证书**"。
    
15. 选择并按住 (，或右键单击证书) ，然后选择 " **复制**"。
    
16. 在树窗格中，打开 "**受信任的根证书颁发机构**"  >  **证书**。
    
17. 将鼠标指针移到已安装证书列表的下方，选择并按住 (或右键单击) ，然后选择 " **粘贴**"。
    
打开管理员级 PowerShell 命令提示符，然后运行以下命令：
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

等待安装完成。
  
按下面这些步骤操作，将 Web 应用程序代理服务配置为使用 ADFS1 作为其联合服务器：
  
1. 选择 " **开始**"，然后选择 " **服务器管理器**"。
    
2. 在树窗格中，选择 " **远程访问**"。
    
3. 在顶部的工具栏中，选择橙色警告符号，然后选择 **"打开 Web 应用程序代理向导"**。
    
4. 在 "Web 应用程序代理配置向导" 的 " **欢迎** " 页上，选择 " **下一步**"。
    
5. 在“联合服务器”页上：****
    
  - 在 " **联合身份验证服务名称** " 框中，输入联合身份验证服务 FQDN。
    
  - 在 " **用户名** " 框中，输入 **CORP \\ User1**。
    
  - 在 " **密码** " 框中，输入 User1 帐户的密码。
    
  - 选择“**下一步**”。
    
6. 在 " **AD FS 代理证书** " 页上，选择向下箭头，选择包含联合身份验证服务 FQDN 的证书，然后选择 " **下一步**"。
    
7. 在 " **确认** " 页上，选择 " **配置**"。
    
8. 在 " **结果** " 页上，选择 " **关闭**"。
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>第 5 阶段：为 Microsoft 365 配置联合标识。

通过 [Azure 门户](https://portal.azure.com)，使用 CORP\\User1 帐户凭据连接 APP1 虚拟机。
  
若要为 Azure AD Connect 和 Microsoft 365 订阅配置联合身份验证，请按照下面这些步骤操作：
  
1. 在桌面上，双击“Azure AD Connect”****。
    
2. 在 " **欢迎使用 AZURE AD Connect** " 页上，选择 " **配置**"。
    
3. 在 " **其他任务** " 页上，选择 " **更改用户登录**"，然后选择 " **下一步**"。
    
4. 在 " **连接到 AZURE AD** " 页上，输入全局管理员帐户名称和密码，然后选择 " **下一步**"。
    
5. 在 " **用户登录** " 页上，选择 " **联盟与 AD FS**"，然后选择 " **下一步**"。
    
6. 在 " **AD fs 场**" 页上，选择 "**使用现有 AD FS 场**"，在 "**服务器名称**" 框中输入**ADFS1** ，然后选择 "**下一步**"。
    
7. 当系统提示输入服务器凭据时，请输入 CORP \\ User1 帐户的凭据，然后选择 **"确定"**。
    
8. 在 "**域管理员**凭据" 页上，在 "**用户名**" 框中输入**CORP \\ User1** ，在 "**密码**" 框中输入帐户密码，然后选择 "**下一步**"。
    
9. 在 " **AD FS 服务帐户**" 页上，在 "**域用户名**" 框中输入**CORP \\ ADFS 服务**，在 "**域用户密码**" 框中输入帐户密码，然后选择 "**下一步**"。
    
10. 在 " **AZURE AD 域** " 页上的 " **域**" 中，选择您之前在第1阶段中创建并添加到订阅中的域的名称，然后选择 " **下一步**"。
    
11. 在 " **准备配置** " 页上，选择 " **配置**"。
    
12. 在 " **安装完成** " 页上，选择 " **验证**"。
    
    您应该会看到表明 intranet 和 internet 配置均已验证的消息。
    
13. 在 " **安装完成** " 页上，选择 " **退出**"。
    
若要证明联合身份验证能够正常运行，请执行以下操作：
  
1. 在本地计算机上打开浏览器的新专用实例，然后转到 [https://admin.microsoft.com](https://admin.microsoft.com)。
    
2. 对于登录凭据，请输入**user1@** \<*the domain created in Phase 1*> 。
    
    例如，如果您的测试域是 **testlab.contoso.com**，则应输入 "user1@testlab.contoso.com"。 按 **tab** 键或允许 Microsoft 365 自动重定向。
    
    现在应该可以看到“**你所用连接不是专用连接**”页。 你会看到这是因为你的 ADFS1 上安装了你的桌面计算机无法验证的自签名证书。 在联合身份验证的生产部署中，将使用受信任的证书颁发机构颁发的证书，你的用户将不会看到此页。
    
3. 在 "**您的连接不是专用**" 页上，选择 "**高级**"，然后** \<*your federation service FQDN*> **选择 "继续"。 
    
4. 在包含虚构组织名称的页上，使用以下凭据登录：
    
  - 该名称的 **CORP\\User1**
    
  - User1 帐户密码
    
    应该会看到“Microsoft Office 主页”页面。****
    
此过程证明了试用订阅与 DC1 上托管的 AD DS corp.contoso.com 域进行了联合。下面是身份验证流程的基本信息：
  
1. 如果你在登录帐户名中使用在第 1 阶段中创建的联盟域，Microsoft 365 将浏览器重定向到联合身份验证服务 FQDN 和 PROXY1。
    
2. PROXY1 向本地计算机发送虚构的公司登录页。
    
3. PROXY1 会将你发送给它的 CORP\\User1 和密码转发给 ADFS1。
    
4. ADFS1 使用 DC1 验证 CORP\\User1 和密码，然后向本地计算机发送安全令牌。
    
5. 本地计算机向 Microsoft 365 发送安全令牌。
    
6. Microsoft 365 验证安全令牌是否由 ADFS1 创建，并在验证通过后允许访问。
    
现在，试用订阅已配置了联合身份验证。可以将此开发/测试环境用于高级身份验证方案。
  
## <a name="next-step"></a>后续步骤

当您准备好在 Azure 中为 Microsoft 365 部署生产就绪、高可用性联合身份验证时，请参阅 [在 azure 中部署适用于 microsoft 365 的高可用性联合身份验证](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)。
  
