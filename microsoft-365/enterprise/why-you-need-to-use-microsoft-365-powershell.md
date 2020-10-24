---
title: 为什么需要使用 PowerShell for Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: 摘要：了解为什么必须使用 PowerShell 来管理 Microsoft 365，在某些情况下，在某些情况下可以更有效地管理 Microsoft。
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754102"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>为什么需要使用 PowerShell for Microsoft 365

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

使用 Microsoft 365 管理中心，可以管理 Microsoft 365 用户帐户和许可证。 您还可以管理 Microsoft 365 服务，例如 Exchange Online、团队和 SharePoint Online。 [！注意] 如果改用 PowerShell 管理这些服务，则可以并利用命令行和脚本语言环境来实现速度、自动化和其他功能。
  
本文介绍如何使用 PowerShell 来管理 Microsoft 365，以执行以下操作：
  
- 显示您在 Microsoft 365 管理中心中无法看到的其他信息
    
- 仅配置 PowerShell 可能的功能和设置
    
- 批量操作
    
- 筛选数据
    
- 打印或保存数据
    
- 跨服务管理
    
请注意，PowerShell for Microsoft 365 是一组用于 Windows PowerShell 的模块，这是一种适用于基于 Windows 的服务和平台的命令行环境。 此环境创建一种命令行管理程序语言，可使用其他模块进行扩展。 它提供了一种执行简单或复杂命令或脚本的方法。 例如，在安装适用于 Microsoft 365 模块的 PowerShell 并连接到 Microsoft 365 订阅后，可以运行以下命令来列出 Microsoft Exchange Online 的所有用户邮箱：
  
```powershell
Get-Mailbox
```

您还可以使用 Microsoft 365 管理中心获取邮箱的列表，但对所有 web 应用程序的所有网站的所有列表中的项目进行计数并不简单。
  
PowerShell for Microsoft 365 旨在帮助您管理 Microsoft 365，而不是取代 Microsoft 365 管理中心。 管理员需要能够使用适用于 Microsoft 365 的 PowerShell，因为某些配置过程只能通过 PowerShell 为 Microsoft 365 命令完成。 在这些情况下，您需要了解如何执行以下操作：
  
- 为 Microsoft 365 模块安装 PowerShell (仅为每个管理员计算机) 执行一次。
    
- 为每个 PowerShell 会话 (一次连接到 Microsoft 365 订阅) 。
    
- 收集运行所需的 PowerShell for Microsoft 365 命令所需的信息。
    
- 为 Microsoft 365 命令运行 PowerShell。
    
了解这些基本技能之后，您无需使用 " **获取邮箱** " 命令列出邮箱用户。 此外，您还无需了解如何创建新命令（如前面提到的命令），以便对所有 web 应用程序的所有网站的所有列表中的所有项进行计数。 Microsoft 和管理员社区可在需要时帮助你执行此类任务。
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>PowerShell for Microsoft 365 可以显示你无法通过 Microsoft 365 管理中心看到的信息

Microsoft 365 管理中心显示了许多有用的信息。 但它不会显示 Microsoft 365 存储的有关用户、许可证、邮箱和网站的所有可能信息。 下面的示例展示了 Microsoft 365 管理中心中的 *用户和组* ：
  
![Microsoft 365 管理中心中的用户和组的显示示例。](../media/o365-powershell-users-and-groups.png)
  
此视图提供了在许多情况下所需的信息。 但是，有时你需要了解更多。 例如，Microsoft 365 许可 (和可用于用户) 的 Microsoft 365 功能取决于用户的地理位置。 您可以扩展到美国居住的用户的策略和功能可能与您可以在印度或比利时的用户中扩展的策略和功能不同。 在 Microsoft 365 管理中心中执行以下步骤，以确定用户的地理位置：
  
1. 双击用户的"显示名称"。
    
2. 在用户属性显示窗格中，选择 " **详细信息**"。
    
3. 在详细信息显示中，选择 " **其他详细信息**"。
    
4. 向内滚动，直到找到 "标题" **国家或地区**：
    
     ![Microsoft 365 管理中心中用户的区域信息示例。](../media/o365-powershell-usage-location.png)
  
5. 在一张纸上记下用户的显示名称和位置，或将其复制并粘贴至记事本中。
    
您必须为每个用户重复此过程。 如果有多个用户，此过程可能很单调。 对于适用于 Microsoft 365 的 PowerShell，可以使用以下命令为所有用户显示此信息：
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core 不支持在其名称中包含 *Msol* 的 Windows PowerShell 模块和 Cmdlet 的 Microsoft Azure Active Directory 模块。 您必须从 Windows PowerShell 中运行这些 cmdlet。
>

下面是结果的一个示例：
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有用户 (**AzureADUser**) ，但仅显示每个用户的名称和位置 (**选择 "DisplayName"、"UsageLocation**) "。
  
由于适用于 Microsoft 365 的 PowerShell 支持命令行管理程序语言，因此您可以进一步操纵 **AzureADUser** 命令获取的信息。 例如，您可能希望按照用户的位置对这些用户进行排序，将所有巴西用户组合在一起，将所有美国用户组合在一起，等等。 以下命令如下所示：
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

下面是结果的一个示例：
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有用户，但仅显示每个用户的名称和位置，并按其位置和名称 (**Sort UsageLocation，DisplayName**) 对其进行排序。
  
您还可以使用其他筛选。 例如，如果您只想查看有关巴西用户的信息，请使用此命令：
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

下面是结果的一个示例：
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的位置是巴西的所有用户 **（在 {$ (其中，{$） \_ 。UsageLocation-eq "BR"}**) 然后显示每个用户的名称和位置。
  
 **关于大型域的说明**
  
如果有成千上万个用户的大型域，请尝试在本文中介绍的一些示例将导致限制。 根据计算功率和可用网络带宽等因素，您可能尝试一次执行太多操作。 大型组织可能希望将其中一些 PowerShell 操作拆分成两个命令。

例如，以下命令返回所有用户帐户并显示每个帐户的名称和位置：
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

这对于较小的域非常有用。 但在大型组织中，可能需要将该操作拆分为两个命令：一个命令，用于将用户帐户信息存储在一个变量中，另一个用于显示所需的信息。 下面是一个示例：
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

此 PowerShell 命令集的解释如下：
1. 获取当前 Microsoft 365 订阅中的所有用户，并将信息存储在名为 $x (**$x = AzureADUser**) 的变量中。
1.  显示变量 *$x*的内容，但只包含每个用户的名称和位置 (**$x |选择 "DisplayName"、"UsageLocation) "** 。
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 具有仅可为 Microsoft 365 配置 PowerShell 的功能

Microsoft 365 管理中心旨在提供适用于大多数环境的常见、有用管理任务的访问权限。 换句话说，Microsoft 365 管理中心的设计是为了使典型管理员可以执行最常见的管理任务。 但有些任务无法在管理中心完成。
  
例如，Skype for Business Online 管理中心提供了用于创建自定义会议邀请的几个选项：
  
![用于在 Skype for Business Online 管理中心内显示自定义会议邀请的示例。](../media/o365-powershell-meeting-invitation.png)
  
借助这些设置，您可以为会议邀请添加少许个性化和专业化。 但与简单地创建自定义会议邀请相比，会议配置设置更多。 例如，默认情况下，会议允许：
  
- 匿名用户获取自动参与每个会议的权限。
    
- 与会者记录会议。
    
- 您组织中的所有用户在加入会议时被指定为演示者。
    
这些设置在 Skype for Business Online 管理中心不可用。 你可以从 PowerShell for Microsoft 365 中控制它们。 以下是禁用这三个设置的命令：
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> 若要运行此命令，您必须安装 [Skype For Business Online PowerShell 模块 ](https://www.microsoft.com/download/details.aspx?id=39366)。
  
此 PowerShell 命令的解释如下：
 
1. 在 "新 Skype for Business Online 会议的设置" (**get-csmeetingconfiguration**) 中，禁用允许匿名用户自动进入会议 (**-AdmitAnonymousUsersByDefault $False**) 。
2.  禁用与会者 (**-AllowConferenceRecording $False**) 录制会议的功能。
3. 请勿将组织中的所有用户指定为演示者 (**-DesignateAsPresenter "None"**) 。
  
若要还原这些默认设置 (启用 "选项") ，请运行以下命令：
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

还有其他类似的方案，这也是为什么管理员应了解如何为 Microsoft 365 命令运行 PowerShell 的原因。
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>适用于 Microsoft 365 的 PowerShell 非常适合用于批量操作

当您执行一个操作时，像 Microsoft 365 管理中心这样的可视界面是最有用的。 例如，如果您需要禁用一个用户帐户，则可以使用管理中心快速查找并清除复选框。 这可能比在 PowerShell 中执行类似的操作更容易。
  
但是，如果您必须在一大范围的其他内容中更改许多内容或所选内容，Microsoft 365 管理中心可能不是最佳工具。 例如，假设您必须更改成千上万个电话号码的前缀，或者从所有 SharePoint Online 网站中删除特定用户 *Ken Myer* 。 如何在 Microsoft 365 管理中心中执行此操作？
  
在最后一个示例中，假设您有几百个 SharePoint Online 网站，并且您不知道哪些 Ken Meyer 是其成员。 您必须从 Microsoft 365 管理中心开始，然后对每个网站执行此过程：
  
1. 选择网站的 **URL** 。
    
2. 在 " **网站集属性** " 框中，选择 "网站 **地址** " 链接以打开网站。
    
3. 在网站上，选择 " **共享**"。
    
4. 在 " **共享** " 对话框中，选择显示有权访问该网站的所有用户的链接：
    
     ![在 SharePoint Online 管理中心内查看 SharePoint Online 站点成员的示例。](../media/o365-powershell-view-permissions.png)
  
5. 在 " **共享** " 对话框中，选择 " **高级**"。
    
6. 向下滚动用户列表，找到并选择 Ken Myer (如果他拥有对网站) 的权限，然后选择 " **删除用户权限**"。
    
对于几百个网站，这可能需要 *很长* 时间。
  
另一种方法是在 PowerShell for Microsoft 365 中运行以下命令，以从所有网站中删除 Ken Myer：
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> 此命令要求您安装 [SharePoint Online PowerShell 模块](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。 
  
此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有 SharePoint 网站 (**get-sposite**) 并为每个网站删除 Ken Meyer （从可访问它的用户列表 (**ForEach {remove-get-spouser-site $） \_ 。Url-Person.loginname "kenmyer \@ litwareinc.com"}**) 。
  
我们将告知 Microsoft 365 从每个站点中删除 Ken Meyer，包括他无权访问的所有站点。 因此，结果将显示他无权访问的那些网站的错误。 我们可以对此命令使用附加条件，以便仅从拥有他的登录列表的站点中删除 Ken Meyer。 但返回的错误对网站本身不造成危害。 此命令可能需要几分钟的时间才能运行数百个网站，而不是通过 Microsoft 365 管理中心工作数小时。
  
下面是另一个批量操作示例。 使用此命令将 *Bonnie Kearney*（一个新的 SharePoint 管理员）添加到组织中的所有网站：
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有 SharePoint 网站，并为每个网站提供 Bonnie Kearney access，具体方法是将其登录名添加到网站的成员组 (**ForEach {get-spouser-site $ \_ 。Url-Person.loginname "bkearney \@ litwareinc.com"-Group "Members"}**) 。
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>适用于 Microsoft 365 的 PowerShell 非常适合筛选数据

Microsoft 365 管理中心提供了几种筛选数据的方法，以便轻松找到目标信息子集。 例如，可以通过 Exchange 轻松筛选用户邮箱的几乎所有属性。 例如，以下是居住在布卢明顿城市中的所有用户的邮箱列表：
  
![在 Microsoft 365 管理中心中执行高级搜索的示例，用于居住在布卢明顿城市的所有用户的邮箱列表。](../media/o365-powershell-advanced-search.png)
  
Exchange 管理中心还允许您组合筛选条件。 例如，您可以查找居住在布卢明顿中的所有人的邮箱，并在财务部门工作。
  
但您可以在 Exchange 管理中心中执行的操作有一些限制。 例如，您无法轻松找到居住在布卢明顿 *或* 圣地亚哥的用户的邮箱，或者无法找到布卢明顿中未居住的所有用户的邮箱。
  
您可以使用以下 PowerShell for Microsoft 365 命令获取邮箱列表，以获取居住在布卢明顿或圣地亚哥的所有人员的邮箱列表：
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

下面是结果的一个示例：
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有用户，这些用户在 San 圣地亚哥或布卢明顿的城市中拥有邮箱（ **其中 {$） (其中的邮箱 \_ 。RecipientTypeDetails-eq "UserMailbox"-和 ($ \_ 。City-eq "圣地亚哥"-或 $ \_ 。City-eq "布卢明顿" ) }**) ，然后显示每个 (的姓名和城市 **选择 "DisplayName"、"city**) "。
  
下面的命令可列出除布卢明顿以外的生活在任何位置的用户的所有邮箱：
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

下面是结果的一个示例：
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的邮箱不位于 (布卢明顿的城市中的所有用户 **{$ \_ 。RecipientTypeDetails-eq "UserMailbox" 和 $ \_ 。City-ne "布卢明顿"}**) ，然后显示每个城市的姓名和城市。
  
### <a name="use-wildcards"></a>使用通配符

您还可以在 PowerShell 筛选器中使用通配符，以匹配名称的一部分。 例如，假设您正在寻找用户帐户。 您可以记住的是，用户的姓是 *Anderson* ，或者可能是 *Henderson* 或 *Jorgenson*。
  
您可以使用搜索工具在 Microsoft 365 管理中心内跟踪该用户并执行三种不同的搜索：
  
- 一次是搜索  *Anderson* 
    
- 一次是搜索  *Henderson* 
    
- 一次是搜索  *Jorgenson* 
    
由于所有这三个名称都以 "儿子" 结束，因此您可以告知 PowerShell 显示姓名以 "儿子" 结尾的所有用户。 以下命令如下所示：
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

此 PowerShell 命令的解释为：获取当前 Microsoft 365 订阅中的所有用户，但使用仅列出姓氏以 "儿子" 结尾的用户的筛选器 (**筛选器 "{LastName-like" 子 \* 儿子 "}"**) 。 \*代表任意一组字符，这些字符是用户的姓氏中的字母。
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>适用于 Microsoft 365 的 PowerShell 可轻松打印或保存数据

Microsoft 365 管理中心允许你查看数据列表。 以下是 Skype for business Online 管理中心的示例，其中显示已为 Skype for business Online 启用的用户的列表：
  
![用于显示已为 Skype for Business Online 启用的用户列表的 Skype for Business Online 管理中心的示例。](../media/o365-powershell-lync-users.png)
  
若要将该信息保存到文件中，则必须将其粘贴到文档或 Microsoft Excel 工作表中。 任意一种情况都可能需要其他格式。 此外，Microsoft 365 管理中心不提供直接打印显示列表的方法。
  
幸运的是，您可以使用 PowerShell 不仅显示列表，还可以将其保存到可轻松导入 Excel 的文件中。 下面的命令示例将 Skype for Business Online 用户数据保存为逗号分隔的值 (CSV) 文件，然后可以在 Excel 工作表中轻松地将其作为表导入：
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

下面是结果的一个示例：
  
![为保存到逗号分隔值文件的 Skype for business Online 用户数据导入到 Excel 工作表中的表的示例。](../media/o365-powershell-data-in-excel.png)
  
此 PowerShell 命令的解释为：在当前 Microsoft 365 订阅中获取所有 Skype for Business Online 用户 (**get-csonlineuser**) ;仅获取用户名、UPN 和位置 (**选择 DisplayName、UserPrincipalName、UsageLocation**) ;，然后将该信息保存在名为 C： logsSfBUsers.csv 的 CSV 文件中 \\ \\ (**导出-CSV-路径 "C： \\ Logs \\SfBUsers.csv"-NoTypeInformation**) 。
  
您还可以使用选项将此列表另存为 XML 文件或 HTML 页面。 事实上，使用其他 PowerShell 命令，您可以将其直接保存为 Excel 文件，并使用所需的任何自定义格式。
  
您还可以向 Windows 中的默认打印机发送直接显示列表的 PowerShell 命令的输出。 下面是一个示例命令：
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

打印的文档如下所示：
  
![在 Windows 中直接发送到默认打印机的 PowerShell 命令输出的打印文档的示例。](../media/o365-powershell-printed-data.png)
  
此 PowerShell 命令的解释为：在当前 Microsoft 365 订阅中获取所有 Skype for Business Online 用户;仅获取用户名称、UPN 和位置;，然后将该信息发送到默认的 Windows 打印机 (**打印机**) 。
  
打印的文档与 PowerShell 命令窗口中显示的简单格式相同。 若要获取硬副本，只需添加 **|打印机** 到命令的末尾。
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>PowerShell for Microsoft 365 允许您跨服务器产品进行管理

组成 Microsoft 365 的组件旨在协同工作。 例如，假设您将一个新用户添加到 Microsoft 365，并指定用户的部门和电话号码等信息。 如果您访问任何 Microsoft 365 服务中的用户信息，则该信息将可用： Skype for Business Online、Exchange 或 SharePoint。
  
不过，此规则适用于跨产品套件的一般信息。 特定于产品的信息（如有关用户的 Exchange 邮箱的信息）通常不在套件中提供。 例如，有关是否启用了用户邮箱的信息仅适用于 Exchange 管理中心。
  
假设您要为您的所有用户生成显示以下信息的报告：
  
- 用户的显示名称
    
- 用户是否已获得适用于 Microsoft 365 的许可
    
- 用户的 Exchange 邮箱是否已启用
    
- 用户是否已启用 Skype for Business Online
    
您无法轻松在 Microsoft 365 管理中心生成此类报告。 相反，您必须创建单独的文档来存储信息，例如 Excel 工作表。 然后，从 Microsoft 365 管理中心获取所有用户名和许可信息，从 Exchange 管理中心获取邮箱信息，从 Skype for business Online 管理中心获取 Skype for Business Online 信息，然后将这些信息组合在一起。
  
另一种方法是使用 PowerShell 脚本为您编译报告。
  
下面的示例脚本比您在本文中已看过的命令更复杂。 但是，它展示了使用 PowerShell 创建难以以其他方式获取的信息视图的可能性。 下面的脚本用于编译和显示所需的列表：
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

下面是结果的一个示例：
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

此 PowerShell 脚本的解释如下：  

1. 获取当前 Microsoft 365 订阅中的所有用户，并将信息存储在名为 *$x* (**$x = AzureADUser**) 的变量中。
1. 启动在变量中的所有用户上运行的循环 $x (**foreach ($i $x **) ) 中。  
1. 定义一个名为 *$y* 的变量，并将用户的邮箱信息存储在其中 (**$y = Get-Mailbox 标识 $i** 。
1. 将新属性添加到名为 *IsMailBoxEnabled*的用户信息中。 将其设置为用户邮箱的 IsMailBoxEnabled 属性的值 (**$i | Add-Member MemberType NoteProperty-Name IsMailBoxEnabled-value $Y IsMailBoxEnabled**) 。
1. 定义一个名为 *$y*的变量，并将用户的 Skype For business Online 信息存储在其中 (**$Y = Get-CsOnlineUser 身份 $i**) 。
1. 将新属性添加到名为 *EnabledForSfB*的用户信息中。 将其设置为用户的 Skype for Business Online 信息的 Enabled 属性的值 (**$i | Add-Member-MemberType NoteProperty-Name EnabledForSfB-value $y。已启用**) 。
1. 显示用户列表，但仅包括其名称、是否已获得许可，以及两个新属性，它们分别指示其邮箱是否已启用以及是否为 Skype for business Online 启用了这些用户 (**$x |选择 DisplayName、IsLicensed、IsMailboxEnabled、EnabledforSfB**) 。
  
## <a name="see-also"></a>另请参阅

[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365 用户帐户、许可证和组](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[使用 Windows PowerShell 在 Microsoft 365 中创建报告](use-windows-powershell-to-create-reports-in-microsoft-365.md)
