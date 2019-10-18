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
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="a44c8-103">轻型基本配置</span><span class="sxs-lookup"><span data-stu-id="a44c8-103">The lightweight base configuration</span></span>

<span data-ttu-id="a44c8-104">本文分步说明了如何使用 Microsoft 365 E5 订阅和运行 Windows 10 企业版的计算机创建简化的环境。</span><span class="sxs-lookup"><span data-stu-id="a44c8-104">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![轻量级 Microsoft 365 企业版测试环境](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="a44c8-106">使用生成的环境来测试 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="a44c8-106">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![适用于 Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="a44c8-108">单击[此处](https://aka.ms/m365etlgstack)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="a44c8-108">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="a44c8-109">第 1 阶段：创建 Office 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="a44c8-109">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="a44c8-110">按照 [Office 365 开发/测试环境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)第 2 和第 3 阶段中的步骤来创建一个轻量级的 Office 365 开发/测试环境。</span><span class="sxs-lookup"><span data-stu-id="a44c8-110">Follow the steps in Phase 2 and Phase 3 of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment) to create a lightweight Office 365 dev/test environment.</span></span>

>[!Note]
><span data-ttu-id="a44c8-111">我们为你创建了 Office 365 的试用版订阅，以便你的开发/测试环境具有与你当前拥有的任何付费版订阅分开的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="a44c8-111">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="a44c8-112">这样分开意味着你可在测试租户中添加和删除用户和组，而不影响生产订阅。</span><span class="sxs-lookup"><span data-stu-id="a44c8-112">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
>
  
## <a name="phase-2-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="a44c8-113">第 2 阶段：Microsoft 365 E5 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="a44c8-113">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="a44c8-114">在该阶段中，可注册 Microsoft 365 E5 试用版订阅，并将其添加到 Office 365 E5 试用版订阅所在的组织中。</span><span class="sxs-lookup"><span data-stu-id="a44c8-114">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="a44c8-115">首先，请添加 Microsoft 365 E5 试用版订阅并向全局管理员帐户分配一个 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="a44c8-115">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="a44c8-116">通过 Internet 浏览器的专用实例，使用全局管理员帐户凭据登录 [http://admin.microsoft.com](http://admin.microsoft.com) 上的 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="a44c8-116">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [http://admin.microsoft.com](http://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="a44c8-117">在“**Microsoft 365 管理中心**”页面上的左侧导航栏中，单击“**计费 > 购买服务**”。</span><span class="sxs-lookup"><span data-stu-id="a44c8-117">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="a44c8-118">在“**购买服务**”页面上，找到“**Microsoft 365 E5**”项目。</span><span class="sxs-lookup"><span data-stu-id="a44c8-118">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="a44c8-119">将鼠标指针悬停在该项目上方并单击“**开始免费试用**”。</span><span class="sxs-lookup"><span data-stu-id="a44c8-119">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="a44c8-120">在“**Microsoft 365 E5 试用版**”页面上，选择接收短信或通话，输入你的电话号码，然后单击“**发短信给我**”或“**打电话给我**”。</span><span class="sxs-lookup"><span data-stu-id="a44c8-120">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="a44c8-121">在“确认订单”页上，单击“立即试用”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a44c8-121">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="a44c8-122">在“订单签收”页中，单击“继续”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a44c8-122">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="a44c8-123">在 Microsoft 365 管理中心中，单击“**活动用户**”，然后单击管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="a44c8-123">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="a44c8-124">对于**产品许可证**，请单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a44c8-124">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="a44c8-125">关闭 Office 365 企业版 E5 的许可证，并打开 Microsoft 365 E5 的许可证。</span><span class="sxs-lookup"><span data-stu-id="a44c8-125">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="a44c8-126">单击“**保存 > 关闭 > 关闭**”。</span><span class="sxs-lookup"><span data-stu-id="a44c8-126">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="a44c8-127">接下来，***如果你完成了*** [Office 365 开发/测试环境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)的第 3 阶段，请为所有其他帐户（用户 2、用户 3、用户 4 和用户 5）重复前述过程的步骤 8 到 11。</span><span class="sxs-lookup"><span data-stu-id="a44c8-127">Next, ***if you completed Phase 3 of the*** [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment), repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a44c8-128">Microsoft 365 E5 试用版订阅的有效期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="a44c8-128">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="a44c8-129">对于永久性测试环境，请将此试用版订阅转换为包含少量许可证的付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="a44c8-129">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="a44c8-130">测试环境现在包含：</span><span class="sxs-lookup"><span data-stu-id="a44c8-130">Your test environment now has:</span></span>
  
- <span data-ttu-id="a44c8-131">Microsoft 365 E5 试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="a44c8-131">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="a44c8-132">所有适当的用户帐户（无论是全局管理员帐户还是全部五个用户帐户）都可以使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="a44c8-132">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="a44c8-133">图 1 显示了所得到的配置，它添加了 Microsoft 365 E5，还同时包含了 Office 365 和企业安全性 + 管理 (EMS)。</span><span class="sxs-lookup"><span data-stu-id="a44c8-133">Figure 1 shows your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
<span data-ttu-id="a44c8-134">**图 1：添加 Microsoft 365 试用版订阅**</span><span class="sxs-lookup"><span data-stu-id="a44c8-134">**Figure 1: Adding the Microsoft 365 trial subscription**</span></span>

![Microsoft 365 企业版测试环境的第 2 阶段](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-3-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="a44c8-136">第 3 阶段：创建 Windows 10 企业版计算机</span><span class="sxs-lookup"><span data-stu-id="a44c8-136">Phase 3: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="a44c8-137">在这一阶段，将运行 Windows 10 企业版的独立计算机创建为物理计算机、虚拟机或 Azure 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a44c8-137">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="a44c8-138">物理计算机</span><span class="sxs-lookup"><span data-stu-id="a44c8-138">Physical computer</span></span>

<span data-ttu-id="a44c8-p104">获取个人计算机并在其上安装 Windows 10 企业版。你可在[此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用。</span><span class="sxs-lookup"><span data-stu-id="a44c8-p104">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="a44c8-141">虚拟机</span><span class="sxs-lookup"><span data-stu-id="a44c8-141">Virtual machine</span></span>

<span data-ttu-id="a44c8-p105">使用你选择的虚拟机监控程序创建一个虚拟机并在其上安装 Windows 10 企业版。你可在[此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用。</span><span class="sxs-lookup"><span data-stu-id="a44c8-p105">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="a44c8-144">Azure 中的虚拟机</span><span class="sxs-lookup"><span data-stu-id="a44c8-144">Virtual machine in Azure</span></span>

<span data-ttu-id="a44c8-p106">要在 Microsoft Azure 中创建 Windows 10 虚拟机，***你必须拥有基于 Visual Studio 的订阅***，以便有权访问 Windows 10 企业版的映像。其他类型的 Azure 订阅（如试用版和付费订阅）均无权访问此映像。有关最新信息，请参阅[在 Azure 中使用 Windows 客户端实现开发/测试方案](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)。</span><span class="sxs-lookup"><span data-stu-id="a44c8-p106">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a44c8-p107">下面的命令集使用最新版 Azure PowerShell。请参阅 [Azure PowerShell cmdlet 入门](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)。这些命令集构建了名为 WIN10 的 Windows 10 企业版虚拟机及其所需的全部基础架构，其中包括资源组、存储帐户和虚拟网络。如果你已熟悉 Azure 基础架构服务，请修改这些说明以适应当前部署的基础架构。</span><span class="sxs-lookup"><span data-stu-id="a44c8-p107">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="a44c8-152">首先，启动 Microsoft PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="a44c8-152">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="a44c8-153">使用以下命令登录 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="a44c8-153">Sign in to your Azure account with the following command.</span></span>
  
```
Connect-AzAccount
```

<span data-ttu-id="a44c8-154">使用以下命令获得订阅名称。</span><span class="sxs-lookup"><span data-stu-id="a44c8-154">Get your subscription name using the following command.</span></span>
  
```
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="a44c8-p108">设置 Azure 订阅。使用正确的名称替换引号内的所有内容（包括 \< 和 > 字符）。</span><span class="sxs-lookup"><span data-stu-id="a44c8-p108">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="a44c8-p109">接下来，创建一个新的资源组。要确定一个唯一的资源组名称，请使用此命令列出你现有的资源组。</span><span class="sxs-lookup"><span data-stu-id="a44c8-p109">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="a44c8-p110">使用这些命令创建新的资源组。使用正确的名称替换引号内的所有内容（包括 \< 和 > 字符）。</span><span class="sxs-lookup"><span data-stu-id="a44c8-p110">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="a44c8-p111">接下来，使用这些命令创建新的虚拟网络和 WIN10 虚拟机。出现提示时，为 WIN10 提供本地管理员帐户的名称和密码，并将这些名称和密码存储在安全位置。</span><span class="sxs-lookup"><span data-stu-id="a44c8-p111">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-4-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="a44c8-163">第 4 阶段：将 Windows 10 计算机加入到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="a44c8-163">Phase 4: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="a44c8-164">在创建具有 Windows 10 企业版的物理计算机或虚拟机之后，使用本地管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a44c8-164">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a44c8-165">对于 Azure 中的虚拟机，使用[这些说明](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)进行连接。</span><span class="sxs-lookup"><span data-stu-id="a44c8-165">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="a44c8-166">接下来，将 WIN10 计算机联接到 Microsoft 365 E5 订阅的 Azure AD 租户中。</span><span class="sxs-lookup"><span data-stu-id="a44c8-166">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="a44c8-167">在 WIN10 计算机的桌面上，依次单击“开始”>“设置”>“帐户”>“访问单位或学校”>“连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a44c8-167">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="a44c8-168">在“设置工作或学校帐户”\*\*\*\* 对话框中，单击“将此设备加入到 Azure Active Directory”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a44c8-168">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="a44c8-169">在**工作或学校帐户**中，键入 Microsoft 365 E5 订阅的全局管理员帐户名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="a44c8-169">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="a44c8-170">在“输入密码”\*\*\*\* 中，键入全局管理员帐户的密码，然后单击“登录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a44c8-170">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="a44c8-171">当提示你确定这是你的组织时，单击“加入”\*\*\*\*，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a44c8-171">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="a44c8-172">关闭“设置”窗口。</span><span class="sxs-lookup"><span data-stu-id="a44c8-172">Close the settings window.</span></span>
    
<span data-ttu-id="a44c8-173">接下来，在 WIN10 计算机上安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="a44c8-173">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="a44c8-174">打开 Microsoft Edge 浏览器，使用全局管理员帐户凭据登录到 Office 门户。</span><span class="sxs-lookup"><span data-stu-id="a44c8-174">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="a44c8-175">如需帮助，请参阅[如何登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="a44c8-175">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="a44c8-176">在“**Microsoft Office 家庭版**”选项卡上，单击“**安装 Office**”。</span><span class="sxs-lookup"><span data-stu-id="a44c8-176">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="a44c8-177">出现应执行的操作提示时，单击“运行”\*\*\*\*，然后针对“用户帐户控制”单击“是”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a44c8-177">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="a44c8-p113">等待 Office 完成安装。当看到“**你已设置完毕!**”时，单击“**关闭**”两次。</span><span class="sxs-lookup"><span data-stu-id="a44c8-p113">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="a44c8-180">图 3 显示生成的环境，其中包括具有以下内容的 WIN10 计算机：</span><span class="sxs-lookup"><span data-stu-id="a44c8-180">Figure 3 shows your resulting environment, which includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="a44c8-181">已联接 Microsoft 365 E5 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="a44c8-181">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="a44c8-182">已注册为 Microsoft Intune (EMS) 中的 Azure AD 设备。</span><span class="sxs-lookup"><span data-stu-id="a44c8-182">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="a44c8-183">已安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="a44c8-183">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="a44c8-184">**图 2：Microsoft 365 测试环境的最终配置**</span><span class="sxs-lookup"><span data-stu-id="a44c8-184">**Figure 2: The final configuration of the Microsoft 365 test environment**</span></span>

![Microsoft 365 企业版测试环境的第 4 阶段](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="a44c8-186">现在可以试验 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="a44c8-186">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="a44c8-187">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a44c8-187">Next steps</span></span>

<span data-ttu-id="a44c8-188">浏览下面这些附加的一系列测试实验室指南：</span><span class="sxs-lookup"><span data-stu-id="a44c8-188">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="a44c8-189">标识</span><span class="sxs-lookup"><span data-stu-id="a44c8-189">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="a44c8-190">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="a44c8-190">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="a44c8-191">信息保护</span><span class="sxs-lookup"><span data-stu-id="a44c8-191">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="a44c8-192">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a44c8-192">See also</span></span>

[<span data-ttu-id="a44c8-193">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="a44c8-193">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a44c8-194">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="a44c8-194">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a44c8-195">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="a44c8-195">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
