---
title: 轻型基本配置
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2019
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
description: 根据本测试实验室指南，可以创建轻型测试环境来测试 Microsoft 365 企业版。
ms.openlocfilehash: a189cb63847f2b95402a864422257a38d1f098d1
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072182"
---
# <a name="the-lightweight-base-configuration"></a>轻型基本配置

本文分步说明了如何使用 Microsoft 365 E5 订阅和运行 Windows 10 企业版的计算机创建简化的环境。 

![轻量级 Microsoft 365 企业版测试环境](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

使用生成的环境来测试 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。

![适用于 Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 单击[此处](https://aka.ms/m365etlgstack)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。

## <a name="phase-1-create-your-office-365-e5-subscription"></a>第 1 阶段：创建 Office 365 E5 订阅

按照 [Office 365 开发/测试环境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)第 2 和第 3 阶段中的步骤来创建一个轻量级的 Office 365 开发/测试环境。

>[!Note]
>我们为你创建了 Office 365 的试用版订阅，以便你的开发/测试环境具有与你当前拥有的任何付费版订阅分开的 Azure AD 租户。 这样分开意味着你可在测试租户中添加和删除用户和组，而不影响生产订阅。
>
  
## <a name="phase-2-add-a-microsoft-365-e5-trial-subscription"></a>第 2 阶段：Microsoft 365 E5 试用版订阅

在该阶段中，可注册 Microsoft 365 E5 试用版订阅，并将其添加到 Office 365 E5 试用版订阅所在的组织中。
  
首先，请添加 Microsoft 365 E5 试用版订阅并向全局管理员帐户分配一个 Microsoft 365 许可证。
  
1. 通过 Internet 浏览器的专用实例，使用全局管理员帐户凭据登录 [http://admin.microsoft.com](http://admin.microsoft.com) 上的 Microsoft 365 管理中心。
    
2. 在“**Microsoft 365 管理中心**”页面上的左侧导航栏中，单击“**计费 > 购买服务**”。
    
3. 在“**购买服务**”页面上，找到“**Microsoft 365 E5**”项目。 将鼠标指针悬停在该项目上方并单击“**开始免费试用**”。

4. 在“**Microsoft 365 E5 试用版**”页面上，选择接收短信或通话，输入你的电话号码，然后单击“**发短信给我**”或“**打电话给我**”。

5. 在“确认订单”页上，单击“立即试用”********。

6. 在“订单签收”页中，单击“继续”********。

7. 在 Microsoft 365 管理中心中，单击“**活动用户**”，然后单击管理员帐户。

8. 对于**产品许可证**，请单击“**编辑**”。

9. 关闭 Office 365 企业版 E5 的许可证，并打开 Microsoft 365 E5 的许可证。

10. 单击“**保存 > 关闭 > 关闭**”。

接下来，***如果你完成了*** [Office 365 开发/测试环境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)的第 3 阶段，请为所有其他帐户（用户 2、用户 3、用户 4 和用户 5）重复前述过程的步骤 8 到 11。
  
> [!NOTE]
> Microsoft 365 E5 试用版订阅的有效期为 30 天。 对于永久性测试环境，请将此试用版订阅转换为包含少量许可证的付费版订阅。 
  
测试环境现在包含：
  
- Microsoft 365 E5 试用版订阅。
- 所有适当的用户帐户（无论是全局管理员帐户还是全部五个用户帐户）都可以使用 Microsoft 365 E5。
    
图 1 显示了所得到的配置，它添加了 Microsoft 365 E5，还同时包含了 Office 365 和企业安全性 + 管理 (EMS)。
  
**图 1：添加 Microsoft 365 试用版订阅**

![Microsoft 365 企业版测试环境的第 2 阶段](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-3-create-a-windows-10-enterprise-computer"></a>第 3 阶段：创建 Windows 10 企业版计算机

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
  
```
Connect-AzAccount
```

使用以下命令获得订阅名称。
  
```
Get-AzSubscription | Sort Name | Select Name
```

设置 Azure 订阅。使用正确的名称替换引号内的所有内容（包括 \< 和 > 字符）。
  
```
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

接下来，创建一个新的资源组。要确定一个唯一的资源组名称，请使用此命令列出你现有的资源组。
  
```
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

使用这些命令创建新的资源组。使用正确的名称替换引号内的所有内容（包括 \< 和 > 字符）。
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

接下来，使用这些命令创建新的虚拟网络和 WIN10 虚拟机。出现提示时，为 WIN10 提供本地管理员帐户的名称和密码，并将这些名称和密码存储在安全位置。
  
```
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
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-4-join-your-windows-10-computer-to-azure-ad"></a>第 4 阶段：将 Windows 10 计算机加入到 Azure AD

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
    
接下来，在 WIN10 计算机上安装 Office 365 专业增强版。
  
1. 打开 Microsoft Edge 浏览器，使用全局管理员帐户凭据登录到 Office 门户。 如需帮助，请参阅[如何登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。
    
2. 在“**Microsoft Office 家庭版**”选项卡上，单击“**安装 Office**”。
    
3. 出现应执行的操作提示时，单击“运行”****，然后针对“用户帐户控制”单击“是”********。
    
4. 等待 Office 完成安装。当看到“**你已设置完毕!**”时，单击“**关闭**”两次。
    
图 3 显示生成的环境，其中包括具有以下内容的 WIN10 计算机：

- 已联接 Microsoft 365 E5 订阅的 Azure AD 租户。
- 已注册为 Microsoft Intune (EMS) 中的 Azure AD 设备。
- 已安装 Office 365 专业增强版。
  
**图 2：Microsoft 365 测试环境的最终配置**

![Microsoft 365 企业版测试环境的第 4 阶段](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
  
现在可以试验 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。
  
## <a name="next-steps"></a>后续步骤

浏览下面这些附加的一系列测试实验室指南：
  
- [标识](m365-enterprise-test-lab-guides.md#identity)
- [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [信息保护](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[部署 Microsoft 365 企业版](deploy-microsoft-365-enterprise.md)

[Microsoft 365 企业版文档](https://docs.microsoft.com/microsoft-365-enterprise/)
