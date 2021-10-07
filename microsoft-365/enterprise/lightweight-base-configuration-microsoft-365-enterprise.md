---
title: 轻型基本配置
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
- admindeeplinkMAC
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用此测试实验室指南创建轻型测试环境，以测试Microsoft 365测试。
ms.openlocfilehash: 742fc93b64d2e3c1d858931eb7dbc591ebcd8e9d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152714"
---
# <a name="the-lightweight-base-configuration"></a>轻型基本配置

*本测试实验室指南可用于企业Microsoft 365和Office 365 企业版环境。*

本文介绍如何创建具有 Microsoft 365 E5 订阅和运行 Windows 10 企业版 的计算机的简化Windows 10 企业版。

![轻型 Microsoft 3656 Enterprise测试环境。](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

创建轻型测试环境包括五个阶段：
- [阶段 1：创建Microsoft 365 E5订阅](#phase-1-create-your-microsoft-365-e5-subscription)
- [第 2 阶段：配置 Office 365 试用版订阅](#phase-2-configure-your-office-365-trial-subscription)
- [第 3 阶段：添加 Microsoft 365 E5 试用版订阅](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [第 4 阶段：创建 Windows 10 企业版计算机](#phase-4-create-a-windows-10-enterprise-computer)
- [第 5 阶段：将 Windows 10 计算机加入到 Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

使用生成的环境来测试企业版 Microsoft 365[的特性和功能](https://www.microsoft.com/microsoft-365/enterprise)。

![Microsoft 云的测试实验室指南。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> 有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请参阅 Microsoft 365 for enterprise Test [Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

>[!NOTE]
>不妨打印这篇文章，以便记录在 30 天的 Office 365 试用版订阅期内需要对此环境使用的特定信息。 可以轻松地将该订阅的试用期再延长 30 天。 对于永久性测试环境，请创建一个包含单独 Azure AD 租户和少量许可证的新付费订阅。

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>阶段 1：创建Microsoft 365 E5订阅

我们首先创建Microsoft 365 E5试用版订阅，然后将Microsoft 365 E5订阅添加到该订阅。

>[!NOTE]
>我们建议你创建订阅的试用Office 365，以便你的测试环境具有独立于你当前拥有的任何付费订阅的 Azure AD 租户。 这种分离意味着可以在测试租户中添加和删除用户和组，而不会影响生产订阅。

要启动 Microsoft 365 E5 试用版订阅，你首先需要一个虚构公司名称和一个新的 Microsoft 帐户。
  
1. 我们建议你将公司名称 Contoso 的变体用作你的公司名称，它是 Microsoft 示例内容中使用的虚构公司，但这并不是必需的。在此记录虚构的公司名称： ![直线。](../media/Common-Images/TableLine.png)
    
2. 要注册新的 Microsoft 帐户，请转到 [https://outlook.com](https://outlook.com)，然后使用新的电子邮件帐户和地址创建一个帐户。此帐户将用于注册 Office 365。
    
    - 在此记录新帐户的名字和姓氏： ![直线。](../media/Common-Images/TableLine.png)
    
    - 在此记录新的电子邮件帐户地址： ![直线。](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>注册 Office 365 E5 试用订阅

1. 在浏览器中，转到 [https://aka.ms/e5trial](https://aka.ms/e5trial) 。
    
2. 在"感谢您选择 Office 365 E5 **页面的步骤** 1 中，输入新的电子邮件帐户地址。
3. 在跟踪订阅过程的步骤 2 中，输入请求的信息，然后执行验证。
4. 在步骤 3 中，输入组织名称，然后输入将成为订阅全局管理员的帐户名称。
5. 在第 4 步中，在此记录登录页面（选择并复制）： ![直线。](../media/Common-Images/TableLine.png)
6. 在此记录用户 ID： ![ 行 ](../media/Common-Images/TableLine.png) 。onmicrosoft.com  
   记录在安全位置输入的密码。
   此值被称为 **“全局管理员名称”**。
7. 选择 **"转到设置"。**
8. 在Office 365 E5安装程序中，选择"继续使用 **组织的.onmicrosoft.com 电子邮件和登录"，** 然后选择"**退出"，稍后继续**。

你应当查看 Microsoft 365 管理中心。
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>第 2 阶段：配置 Office 365 试用版订阅

在这个阶段，你为订阅配置其他用户，并向这些用户分配 Office 365 E5 许可证。
  
若要从计算机使用 Azure Active Directory PowerShell for Graph 模块连接到订阅，请使用 连接 中的说明Microsoft 365 [PowerShell 进行连接](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
    
在 **"Windows PowerShell凭据** 请求"对话框中，输入全局管理员 (例如，jdoe@contosotoycompany.onmicrosoft.com) 密码。 
  
填写组织名称 (例如 *contosotoycompany*) 、所在位置的两字符国家/地区代码、公用帐户密码，然后从 PowerShell 提示符处运行以下命令：

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License

for($i=2;$i -le 4; $i++) {
    $userUPN= "user$($i)@$($orgName).onmicrosoft.com"
    New-AzureADUser -DisplayName "User $($i)" -GivenName User -SurName $i -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user$($i)"
    $userObjectID = (Get-AzureADUser -SearchString $userupn).ObjectID
    Set-AzureADUserLicense -ObjectId $userObjectID -AssignedLicenses $LicensesToAssign
}
```
> [!NOTE]
> 此处使用公用密码旨在自动配置测试环境，简化配置过程。 显然，对于生产订阅，这是非常不鼓励的。 

### <a name="record-key-information-for-future-reference"></a>记录关键信息供将来参考

如果尚未记录这些值，请现在录制它们：
  
- 全局管理员名称： ![直线。](../media/Common-Images/TableLine.png).onmicrosoft.com（在第 1 阶段的第 6 步中）
    
    此外，还应将此帐户的密码记录在安全位置。
    
- 试用订阅组织名称： ![直线。](../media/Common-Images/TableLine.png) （在第 1 阶段的第 4 步中）
    
- 要列出 User 2、User 3、User 4 和 User 5 的帐户，从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    在此记录帐户名称：
    
  - 用户 2 帐户名：user2@![直线。](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - 用户 3 帐户名：user3@![直线。](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - 用户 4 帐户名：user4@![直线。](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - 用户 5 帐户名：user5@![直线。](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    此外，在安全位置记录这些帐户的公用密码。
   
### <a name="using-an-office-365-test-environment"></a>使用 Office 365 测试环境

如果您只需要一Office 365测试环境，则无需阅读本文的其余部分。

有关适用于 Office 365 和 Microsoft 365 的其他测试实验室Microsoft 365，请参阅 Microsoft 365[企业测试实验室指南](m365-enterprise-test-lab-guides.md)。
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>第 3 阶段：添加 Microsoft 365 E5 试用版订阅

在该阶段中，可注册 Microsoft 365 E5 试用版订阅，并将其添加到 Office 365 E5 试用版订阅所在的组织中。
  
首先，请添加 Microsoft 365 E5 试用版订阅并向全局管理员帐户分配一个新的 Microsoft 365 许可证。
  
1. 在 Internet 浏览器专用窗口中，使用全局管理员帐户凭据登录到 Microsoft 365 管理中心 位置 [https://admin.microsoft.com](https://admin.microsoft.com) 。
    
2. On the **Microsoft 365 管理中心** page， in the left navigation， select **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**Purchase services**</a>.
    
3. 在"**购买服务**"页上 **，Microsoft 365 E5"，** 然后选择"**获取免费试用版"。**

4. 在 **"Microsoft 365 E5"** 页面上，决定接收短信或电话呼叫，输入电话号码，然后选择"给我发短信"或"**呼叫我"。** 执行验证。

5. 在"**确认订单"页上**，选择"**立即试用"。**

6. 在"**订单收据"** 页上，选择"继续 **"。**

7. 在"Microsoft 365 管理中心"中，选择"**用户**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**""活动用户"。**</a>

8. 在 **"活动用户"** 中，选择管理员帐户。

9. 选择 **"许可证和应用"。**

10. 禁用 Office 365 企业版 E5 的许可证，并启用 Microsoft 365 E5 的许可证。

11. 选择 **"保存更改**"，然后关闭用户帐户信息窗格。

接下来，对其他所有帐户（用户 2、用户 3、用户 4 和用户 5）重复执行上面过程的第 8 步到第 11 步。
  
> [!NOTE]
> 试用版订阅Microsoft 365 E5 30 天。 对于永久测试环境，将此试用版订阅转换为带少量许可证的付费订阅。
  
测试环境现在包含：
  
- Microsoft 365 E5 试用版订阅。
- 所有适当的用户帐户（无论是全局管理员帐户还是全部五个用户帐户）都可以使用 Microsoft 365 E5。
    
生成的配置（可添加Microsoft 365 E5）如下所示：
  
![Microsoft 3656 测试环境的第 3 Enterprise阶段。](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>第 4 阶段：创建 Windows 10 企业版计算机

在这一阶段，将运行 Windows 10 企业版的独立计算机创建为物理计算机、虚拟机或 Azure 虚拟机。
  
### <a name="physical-computer"></a>物理计算机

在个人计算机上，安装Windows 10 企业版。 你可以在此处下载[Windows 10 企业版试用版。](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)
  
### <a name="virtual-machine"></a>虚拟机

使用你选择的虚拟机监控程序创建虚拟机，然后Windows 10 企业版虚拟机。 你可以在此处下载[Windows 10 企业版试用版。](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)
  
### <a name="virtual-machine-in-azure"></a>Azure 中的虚拟机

要在 Microsoft Azure 中创建 Windows 10 虚拟机，***你必须拥有基于 Visual Studio 的订阅***，以便有权访问 Windows 10 企业版的映像。其他类型的 Azure 订阅（如试用版和付费订阅）均无权访问此映像。有关最新信息，请参阅 [在 Azure 中使用 Windows 客户端实现开发/测试方案](/azure/virtual-machines/windows/client-images)。
  
> [!NOTE]
> [!注意] 下面的命令集使用最新版 Azure PowerShell。 请参阅 [Get started with Azure PowerShell cmdlets](/powershell/azureps-cmdlets-docs/)（Azure PowerShell cmdlet 使用入门）。 这些命令集构建Windows 10 企业版 WIN10 及其所有必需基础结构（包括资源组、存储帐户和虚拟网络）的虚拟机。 如果你已熟悉 Azure 基础结构服务，请根据当前部署的基础结构调整这些说明。
  
首先，启动 Microsoft PowerShell 提示符。
  
使用此命令登录 Azure 帐户。
  
```powershell
Connect-AzAccount
```

使用此命令获取订阅名称。
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

设置 Azure 订阅。 用正确的名称替换引号内 \< and > 的所有内容（包括字符）。
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

接下来，创建一个新的资源组。要确定一个唯一的资源组名称，请使用此命令列出你现有的资源组。
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

使用这些命令创建新的资源组。 用正确的名称替换引号内 \< and > 的所有内容（包括字符）。
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

接下来，使用这些命令创建新的虚拟网络和 WIN10 虚拟机。 当系统提示时，提供 WIN10 的本地管理员帐户的名称和密码，并存储在安全的位置。
  
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
> 对于 Azure 中的虚拟机，请使用  [以下](/azure/virtual-machines/windows/connect-logon) 说明进行连接。
  
接下来，将 WIN10 计算机联接到 Microsoft 365 E5 订阅的 Azure AD 租户中。
  
1. 在 WIN10 计算机的桌面上，选择"开始> 设置 >**帐户>访问工作或学校> 连接。**
    
2. 在 **"设置工作或学校帐户**"对话框中，选择 **"加入此设备以Azure Active Directory"。**
    
3. 在 **"工作或学校帐户**"中，输入你的订阅的全局管理员Microsoft 365 E5名称，然后选择"下一步 **"。**
    
4. 在 **"输入密码**"中，输入全局管理员帐户的密码，然后选择"**登录"。**
    
5. 当系统提示确保这是您的组织时，请选择"**加入**"，然后选择"完成 **"。**
    
6. 关闭“设置”窗口。
    
接下来，Microsoft 365 企业应用版 WIN10 计算机上安装以下组件：
  
1. 打开 Microsoft Edge 浏览器，然后使用全局[Microsoft 365 管理中心帐户凭据](https://admin.microsoft.com)登录该浏览器。
    
2. 在 **"Microsoft Office主页"** 选项卡上，选择"**安装Office"。**
    
3. 当系统提示要执行哪些操作时，请选择"**运行**"，然后 **为"用户帐户** 控制 **"选择"是"。**
    
4. 等待Office完成安装。 当你看到" **你已全部设置！"时，** 选择"关闭 **"两** 次。
    
生成的环境如下所示：

![Microsoft 3656 测试环境的第 5 Enterprise阶段。](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

这包括符合以下条件的 WIN10 计算机：

- 已联接 Microsoft 365 E5 订阅的 Azure AD 租户。
- 已注册为 Microsoft Intune (EMS) 中的 Azure AD 设备。
- Microsoft 365 企业应用版安装。
  
现在，你已准备好试用适用于企业的 Microsoft 365[功能](https://www.microsoft.com/microsoft-365/enterprise)。
  
## <a name="next-steps"></a>后续步骤

浏览下面这些附加的一系列测试实验室指南：
  
- [标识](m365-enterprise-test-lab-guides.md#identity)
- [移动设备管理](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [信息保护](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)
