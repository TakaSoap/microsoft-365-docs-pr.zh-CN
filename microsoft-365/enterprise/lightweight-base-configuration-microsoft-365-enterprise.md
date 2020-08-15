---
title: 轻型基本配置
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
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
description: 使用此测试实验室指南创建用于测试适用于企业的 Microsoft 365 的轻型测试环境。
ms.openlocfilehash: 5de9e44f83d4c6bbae2b4148ce39ca371ead2d34
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686774"
---
# <a name="the-lightweight-base-configuration"></a>轻型基本配置

*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*

本文分步说明了如何使用 Microsoft 365 E5 订阅和运行 Windows 10 企业版的计算机创建简化的环境。 

![轻量级 Microsoft 365 企业版测试环境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

使用生成的环境测试 [适用于企业的 Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 单击 Microsoft 365 for 企业测试实验室指南堆栈365中的所有文章的可视化地图，然后单击 [microsoft for 企业测试实验室指南堆栈](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) 。

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>第1阶段：创建 Microsoft 365 E5 订阅

我们首先使用 Microsoft 365 E5 试用订阅，然后向其添加 Microsoft 365 E5 订阅。

要启动 Microsoft 365 E5 试用版订阅，你首先需要一个虚构公司名称和一个新的 Microsoft 帐户。
  
1. 我们建议你将公司名称 Contoso 的变体用作你的公司名称，它是 Microsoft 示例内容中使用的虚构公司，但这并不是必需的。在此记录虚构的公司名称： ![折线图](../media/Common-Images/TableLine.png)
    
2. 要注册新的 Microsoft 帐户，请转到 [https://outlook.com](https://outlook.com)，然后使用新的电子邮件帐户和地址创建一个帐户。此帐户将用于注册 Office 365。
    
  - 在此记录新帐户的名字和姓氏： ![折线图](../media/Common-Images/TableLine.png)
    
  - 在此记录新的电子邮件帐户地址： ![折线图](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>注册 Office 365 E5 试用订阅

1. 在计算机上打开 Internet 浏览器，转到 [https://aka.ms/e5trial](https://aka.ms/e5trial)。
    
2. 在“感谢选择 Office 365 E5”**** 页面上，指定第 1 步中的新电子邮件帐户地址。
3. 在跟踪订阅过程的第 2 步中，键入请求的信息，然后执行验证。
4. 在第 3 步中，依次键入组织名称和将成为该订阅的全局管理员的帐户名称。 
5. 在第 4 步中，在此记录登录页面（选择并复制）： ![折线图](../media/Common-Images/TableLine.png) 
6. 在此记录用户 ID：![Line](../media/Common-Images/TableLine.png).onmicrosoft.com  
   将你键入的密码记录在安全的位置。
   此值被称为 **“全局管理员名称”**。
8. 选择“转到设置”****。
9. 在 Office 365 E5 设置中，单击邮件的“继续使用 organization **.onmicrosoft.com 并登录”*，* 然后单击“退出**，**稍后再继续”。**

你应当查看 Microsoft 365 管理中心。
  
我们为你创建了 Office 365 的试用版订阅，以便你的测试环境具有与你当前拥有的任何付费版订阅分开的 Azure AD 租户。 这样分开意味着你可在测试租户中添加和删除用户和组，而不影响生产订阅。
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>第 2 阶段：配置 Office 365 试用版订阅

在这个阶段，你为订阅配置其他用户，并向这些用户分配 Office 365 E5 许可证。
  
使用 " [连接到 Microsoft 365 With PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) " 中的说明，通过计算机从 Azure Active Directory PowerShell for Graph 模块连接到你的订阅。
    
在“Windows PowerShell 凭据请求”**** 对话框中，键入全局管理员名称（例如“jdoe@contosotoycompany.onmicrosoft.com”）和密码。
  
填写组织名称（示例：contosotoycompany）、你所在位置的两位字符的国家/地区代码以及通用帐户密码，然后 PowerShell 提示符中运行以下命令：

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
> 此处使用公用密码旨在自动配置测试环境，简化配置过程。 显然，对于生产订阅，这是非常不鼓励的。 

### <a name="record-key-information-for-future-reference"></a>记录关键信息供将来参考

不妨打印这篇文章，以便记录在 30 天的 Office 365 试用版订阅期内需要对此环境使用的特定信息。 可以轻松地将该订阅的试用期再延长 30 天。 对于永久性测试环境，请创建一个包含单独 Azure AD 租户和少量许可证的新付费订阅。

请记录以下值：
  
- 全局管理员名称： ![折线图](../media/Common-Images/TableLine.png).onmicrosoft.com（在第 1 阶段的第 6 步中）
    
    此外，还应将此帐户的密码记录在安全位置。
    
- 试用订阅组织名称： ![折线图](../media/Common-Images/TableLine.png) （在第 1 阶段的第 4 步中）
    
- 要列出 User 2、User 3、User 4 和 User 5 的帐户，从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    在此记录帐户名称：
    
  - 用户 2 帐户名：user2@![折线图](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - 用户 3 帐户名：user3@![折线图](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - 用户 4 帐户名：user4@![折线图](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - 用户 5 帐户名：user5@![折线图](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    此外，在安全位置记录这些帐户的公用密码。
   

### <a name="using-an-office-365-test-environment"></a>使用 Office 365 测试环境

如果你只需要一个 Office 365 测试环境，则可以在此处停止。 

有关适用于 Office 365 和 Microsoft 365 的其他测试实验室指南，请参阅适用于 [企业测试实验室指南的 Microsoft 365](m365-enterprise-test-lab-guides.md) 。
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>第 3 阶段：添加 Microsoft 365 E5 试用版订阅

在该阶段中，可注册 Microsoft 365 E5 试用版订阅，并将其添加到 Office 365 E5 试用版订阅所在的组织中。
  
首先，请添加 Microsoft 365 E5 试用版订阅并向全局管理员帐户分配一个新的 Microsoft 365 许可证。
  
1. 通过 Internet 浏览器的专用实例，使用全局管理员帐户凭据登录 [https://admin.microsoft.com](https://admin.microsoft.com) 上的 Microsoft 365 管理中心。
    
2. 在“**Microsoft 365 管理中心**”页面上的左侧导航栏中，单击“**计费 > 购买服务**”。
    
3. 在“采购服务”**** 页面上，依次单击“Microsoft 365 E5”**** 和“获取免费试用”****。

4. 在“**Microsoft 365 E5 试用版**”页面上，选择接收短信或通话，输入你的电话号码，然后单击“**发短信给我**”或“**打电话给我**”。 执行验证。

5. 在“确认订单”页上，单击“立即试用”********。

6. 在“订单签收”页中，单击“继续”********。

7. 在“Microsoft 365 管理中心”中，单击“用户”>“活动用户”****。

8. 在“活动用户”**** 中，单击“管理员帐户”。

9. 单击“许可证和应用”****。

10. 禁用 Office 365 企业版 E5 的许可证，并启用 Microsoft 365 E5 的许可证。

11. 单击“保存更改”****，然后关闭“用户帐户信息”窗格。

接下来，对其他所有帐户（用户 2、用户 3、用户 4 和用户 5）重复执行上面过程的第 8 步到第 11 步。
  
> [!NOTE]
> Microsoft 365 E5 试用版订阅的有效期为 30 天。 对于永久测试环境，将此试用版订阅转换为带少量许可证的付费订阅。 
  
测试环境现在包含：
  
- Microsoft 365 E5 试用版订阅。
- 所有适当的用户帐户（无论是全局管理员帐户还是全部五个用户帐户）都可以使用 Microsoft 365 E5。
    
下面是生成的配置，它将添加 Microsoft 365 E5。
  
![Microsoft 365 企业版测试环境的第 3 阶段](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>第 4 阶段：创建 Windows 10 企业版计算机

在这一阶段，将运行 Windows 10 企业版的独立计算机创建为物理计算机、虚拟机或 Azure 虚拟机。
  
### <a name="physical-computer"></a>物理计算机

获取个人计算机并在其上安装 Windows 10 企业版。你可在[此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用。
  
### <a name="virtual-machine"></a>虚拟机

使用你选择的虚拟机监控程序创建一个虚拟机并在其上安装 Windows 10 企业版。你可在[此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用。
  
### <a name="virtual-machine-in-azure"></a>Azure 中的虚拟机

要在 Microsoft Azure 中创建 Windows 10 虚拟机，***你必须拥有基于 Visual Studio 的订阅***，以便有权访问 Windows 10 企业版的映像。其他类型的 Azure 订阅（如试用版和付费订阅）均无权访问此映像。有关最新信息，请参阅[在 Azure 中使用 Windows 客户端实现开发/测试方案](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)。
  
> [!NOTE]
> 下面的命令集使用最新版 Azure PowerShell。请参阅 [Azure PowerShell cmdlet 入门](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)。这些命令集构建了名为 WIN10 的 Windows 10 企业版虚拟机及其所需的全部基础架构，其中包括资源组、存储帐户和虚拟网络。如果你已熟悉 Azure 基础架构服务，请修改这些说明以适应当前部署的基础架构。 
  
首先，启动 Microsoft PowerShell 提示符。
  
使用以下命令登录 Azure 帐户。
  
```powershell
Connect-AzAccount
```

使用以下命令获得订阅名称。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

设置 Azure 订阅。使用正确的名称替换引号内的所有内容（包括 \< and > 字符）。
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

接下来，创建一个新的资源组。要确定一个唯一的资源组名称，请使用此命令列出你现有的资源组。
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

使用这些命令创建新的资源组。使用正确的名称替换引号内的所有内容（包括 \< and > 字符）。
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

接下来，使用这些命令创建新的虚拟网络和 WIN10 虚拟机。出现提示时，为 WIN10 提供本地管理员帐户的名称和密码，并将这些名称和密码存储在安全位置。
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>第 5 阶段：将 Windows 10 计算机加入到 Azure AD

在创建具有 Windows 10 企业版的物理计算机或虚拟机之后，使用本地管理员帐户登录。
  
> [!NOTE]
> 对于 Azure 中的虚拟机，使用[这些说明](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)进行连接。
  
接下来，将 WIN10 计算机联接到 Microsoft 365 E5 订阅的 Azure AD 租户中。
  
1. 在 WIN10 计算机的桌面上，依次单击“开始”>“设置”>“帐户”>“访问单位或学校”>“连接”****。
    
2. 在“设置工作或学校帐户”**** 对话框中，单击“将此设备加入到 Azure Active Directory”****。
    
3. 在**工作或学校帐户**中，键入 Microsoft 365 E5 订阅的全局管理员帐户名称，然后单击“**下一步**”。
    
4. 在“输入密码”**** 中，键入全局管理员帐户的密码，然后单击“登录”****。
    
5. 当提示你确定这是你的组织时，单击“加入”****，然后单击“完成”****。
    
6. 关闭“设置”窗口。
    
接下来，在 WIN10 计算机上安装 Microsoft 365 企业应用版。
  
1. 打开 Microsoft Edge 浏览器，并使用全局管理员帐户凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com) 。
    
2. 在“**Microsoft Office 家庭版**”选项卡上，单击“**安装 Office**”。
    
3. 出现应执行的操作提示时，单击“运行”****，然后针对“用户帐户控制”单击“是”********。
    
4. 等待 Office 完成安装。当看到“**你已设置完毕!**”时，单击“**关闭**”两次。
    
下面是生成的环境。

![Microsoft 365 企业版测试环境的第 5 阶段](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

这包括符合以下条件的 WIN10 计算机：

- 已联接 Microsoft 365 E5 订阅的 Azure AD 租户。
- 已注册为 Microsoft Intune (EMS) 中的 Azure AD 设备。
- 已安装 Microsoft 365 企业应用版。
  
现在，你可以试用 [Microsoft 365 for 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。
  
## <a name="next-steps"></a>后续步骤

浏览下面这些附加的一系列测试实验室指南：
  
- [标识](m365-enterprise-test-lab-guides.md#identity)
- [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [信息保护](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
