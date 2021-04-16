---
title: 如何在 Linux 上部署适用于 Endpoint 的 Defender 和安装
description: 了解如何在 Linux 上部署适用于 Endpoint 的具有安装版本的 Defender
keywords: 'microsoft， defender， atp， linux， 扫描， 防病毒， microsoft defender for endpoint (linux) '
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 362222e4737b1a8dd6b8a0a284bf3bfb1903c288
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861440"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="12a9e-104">在 Linux 上部署适用于终结点的 Defender 和安装</span><span class="sxs-lookup"><span data-stu-id="12a9e-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="12a9e-105">开始之前：</span><span class="sxs-lookup"><span data-stu-id="12a9e-105">Before you begin:</span></span>

- <span data-ttu-id="12a9e-106">安装解压缩（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="12a9e-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="12a9e-107">已安装开发组件，并且存在一个 Repositor 存储库 (生成存储库) 以存储将用于部署到 Endpoint 托管 Linux 服务器上 Defender for Endpoint 的指南 <reponame> 。</span><span class="sxs-lookup"><span data-stu-id="12a9e-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="12a9e-108">可以通过从你的存储库内的"手册"文件夹内运行以下命令，在现有的存储库中创建新的手册：</span><span class="sxs-lookup"><span data-stu-id="12a9e-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="12a9e-109">此命令将为名为 mdatp 的新手册创建新的文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="12a9e-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="12a9e-110">如果你已经有一本要用于将 MDE 部署添加到其中的指南，也可以使用现有手册。</span><span class="sxs-lookup"><span data-stu-id="12a9e-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="12a9e-111">创建手册后，在刚刚创建的手册文件夹内创建一个文件文件夹：</span><span class="sxs-lookup"><span data-stu-id="12a9e-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="12a9e-112">将可以从 Microsoft Defender 安全中心门户下载的 Linux Server 载入 zip 文件转移到此新文件文件夹。</span><span class="sxs-lookup"><span data-stu-id="12a9e-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="12a9e-113">On the Recipe Workstation， navigate to the mdatp/recipes folder.</span><span class="sxs-lookup"><span data-stu-id="12a9e-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="12a9e-114">此文件夹是在生成手册时创建的。</span><span class="sxs-lookup"><span data-stu-id="12a9e-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="12a9e-115">使用首选文本编辑器 (vi 或 nano) 将以下说明添加到 default.rb 文件的末尾：</span><span class="sxs-lookup"><span data-stu-id="12a9e-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="12a9e-116">include_recipe"：：onboard_mdatp"</span><span class="sxs-lookup"><span data-stu-id="12a9e-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="12a9e-117">include_recipe"：：install_mdatp"</span><span class="sxs-lookup"><span data-stu-id="12a9e-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="12a9e-118">然后保存并关闭 default.rb 文件。</span><span class="sxs-lookup"><span data-stu-id="12a9e-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="12a9e-119">接下来，在食谱文件夹中创建一个名为 install_mdatp.rb 的新食谱文件，并在此文件中添加此文本：</span><span class="sxs-lookup"><span data-stu-id="12a9e-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

<span data-ttu-id="12a9e-120">你需要修改版本号、分发和存储库名称，以匹配你要部署到的版本和你要部署的频道。</span><span class="sxs-lookup"><span data-stu-id="12a9e-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="12a9e-121">接下来，应在 mdatp/recipies onboard_mdatp创建一个 onboard_mdatp.rb 文件。</span><span class="sxs-lookup"><span data-stu-id="12a9e-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="12a9e-122">将以下文本添加到该文件：</span><span class="sxs-lookup"><span data-stu-id="12a9e-122">Add the following text to that file:</span></span>

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

<span data-ttu-id="12a9e-123">请确保将路径名称更新到载入文件的位置。</span><span class="sxs-lookup"><span data-stu-id="12a9e-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="12a9e-124">若要测试在部署工作站上部署它，只需运行 ``sudo chef-client -z -o mdatp`` 。</span><span class="sxs-lookup"><span data-stu-id="12a9e-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="12a9e-125">部署后，你应考虑根据为适用于 Linux 的 Microsoft Defender ATP 设置首选项 -Windows 安全中心，考虑创建配置文件并部署到  [|Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences)。</span><span class="sxs-lookup"><span data-stu-id="12a9e-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender ATP for Linux - Windows security | Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span></span>  
<span data-ttu-id="12a9e-126">创建并测试配置文件后，你可以将该文件放置到指南/mdatp/files文件夹中，其中还放置了载入程序包。</span><span class="sxs-lookup"><span data-stu-id="12a9e-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="12a9e-127">然后，可以在 mdatp/recipies 文件夹中创建 settings_mdatp.rb 文件并添加以下文本：</span><span class="sxs-lookup"><span data-stu-id="12a9e-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

<span data-ttu-id="12a9e-128">若要将此步骤作为食谱的一部分，只需include_recipe"：：settings_mdatp"添加到食谱文件夹中的 default.rb 文件。</span><span class="sxs-lookup"><span data-stu-id="12a9e-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="12a9e-129">还可使用 crontab 安排自动更新[计划 Microsoft Defender for Endpoint (Linux) 。 ](linux-update-MDE-Linux.md)</span><span class="sxs-lookup"><span data-stu-id="12a9e-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="12a9e-130">卸载 MDATP 手册：</span><span class="sxs-lookup"><span data-stu-id="12a9e-130">Uninstall MDATP cookbook:</span></span>

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

