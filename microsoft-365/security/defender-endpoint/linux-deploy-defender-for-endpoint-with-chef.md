---
title: 如何在 Linux 上部署适用于 Endpoint 的 Defender 和安装
description: 了解如何在 Linux 上部署适用于 Endpoint 的 Defender 和安装
keywords: 'microsoft， defender， atp， linux， 扫描， 防病毒， microsoft defender for endpoint (linux) '
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 799fc4d163b120b4197b6cd044efe4740e4a3cc7
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61941920"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>通过 Chef 在 Linux 上部署 Defender for Endpoint

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

开始之前：安装解压缩（如果尚未安装）。

已安装开发组件，并且存在一个" (存储库") 生成存储库，以存储将用于部署到 Endpoint 托管 Linux 服务器上 Defender for Endpoint 的指南 \<reponame\> 。

可以通过从你的存储库内的"手册"文件夹内运行以下命令，在现有的存储库中创建新的手册：

```bash
chef generate cookbook mdatp
```

此命令将为名为 mdatp 的新手册创建新的文件夹结构。 如果你已经有一本要用于将 MDE 部署添加到其中的指南，也可以使用现有手册。
创建手册后，在刚刚创建的手册文件夹内创建一个文件文件夹：

```bash
mkdir mdatp/files
```

将可以从 Microsoft 365 Defender 门户下载的 Linux Server 载入 zip 文件转移到此新文件文件夹。

On the Recipe Workstation， navigate to the mdatp/recipes folder. 此文件夹是在生成手册时创建的。 使用首选文本编辑器 (vi 或 nano) 将以下说明添加到 default.rb 文件的末尾：

- include_recipe"：：onboard_mdatp"
- include_recipe"：：install_mdatp"

然后保存并关闭 default.rb 文件。

接下来，在食谱文件夹中创建一个名为 install_mdatp.rb 的新食谱文件，并在此文件中添加此文本：

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
   uri                "https://packages.microsoft.com/config/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/config/rhel/7/prod/"
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

你需要修改版本号、分发和存储库名称，以匹配你要部署到的版本和你要部署的频道。
接下来，应在 mdatp/recipies onboard_mdatp创建一个 onboard_mdatp.rb 文件。 将以下文本添加到该文件：

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

请确保将路径名称更新为载入文件的位置。
若要测试在部署工作站上部署它，只需运行 ``sudo chef-client -z -o mdatp`` 。
部署后，你应考虑根据在 Linux 上设置 Microsoft Defender for Endpoint 的首选项，创建配置文件并 [部署到服务器](/linux-preferences.md)。
创建并测试配置文件后，你可以将该文件放置到指南/mdatp/files文件夹中，其中还放置了载入程序包。 然后，可以在 mdatp/recipies settings_mdatp创建一个 settings_mdatp.rb 文件并添加以下文本：

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

若要将此步骤作为食谱的一部分包含，只需include_recipe"：：settings_mdatp"添加到食谱文件夹中的 default.rb 文件中。
还可使用 crontab 安排自动更新[计划 Microsoft Defender for Endpoint (Linux) 。 ](linux-update-MDE-Linux.md)

卸载 MDATP 手册：

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
