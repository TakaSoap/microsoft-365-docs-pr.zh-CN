---
title: 为开发/测试环境中的文件提供安全的团队
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 摘要：在 Microsoft Teams 中，为开发/测试环境中的文件创建敏感和高度机密团队。
ms.openlocfilehash: 7af36e5a3af94297124c6f03cdead514ac941e5b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082247"
---
# <a name="secure-teams-for-files-in-a-devtest-environment"></a>为开发/测试环境中的文件提供安全的团队

本文提供了创建开发/测试环境的分步说明，包括为[保护 Microsoft Teams 中的文件](secure-files-in-teams.md)解决方案提供敏感和高度机密团队。
  
![在 Microsoft Teams 中，为文件创建敏感和高度机密团队。](../../media/sensitive-highly-confidential-teams-dev-test.png)
  
在生产中部署这些类型的团队前，可使用此开发/测试环境试验和微调设置以满足你的特定需求。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>阶段 1：构建 Microsoft 365 企业版测试环境。

如果只需要测试达到最低要求的轻型敏感和高度机密团队，请按照[轻型基本配置](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)中的说明进行操作。

如果想要在模拟企业中测试敏感和高度机密的团队，请按照[密码哈希同步](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)中的说明进行操作。

>[!Note]
>测试敏感和高度机密团队不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟内部网和 Active Directory 域服务 (AD DS) 林的目录同步。 它在此处作为一个选项提供，以便你可以测试敏感和高度机密团队，并在代表典型组织的环境中对其进行试验。
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>阶段 2：创建和配置 Azure Active Directory (AD) 组和用户

此阶段为虚构组织创建和配置 Azure AD 组和用户。
  
首先，通过 Azure 门户为典型组织创建两个组。
  
1. 在浏览器中创建单独的选项卡，然后转到 Azure 门户，网址为 [https://portal.azure.com](https://portal.azure.com)。 如有需要，请使用 Microsoft 365 E5 试用或已付款订阅的全局管理员帐户凭据登录。
    
2. 在 Azure 门户中，单击“**Azure Active Directory”>“组**”。
    
3. 在“**组 - 所有组**”边栏选项卡上，单击“**+ 新建组**”。
    
4. 在“**组**”边栏选项卡上：
    
  - 在“组类型”中选择“安全性”********。
    
  - 在“**名称**”中键入**高层管理人员**。
    
  - 在“**成员身份**”类型中，选择“**已分配**”。
      
5. 单击“**创建**”，然后关闭“**组**”边栏选项卡。
    
6.  对名为“市场营销人员”的新组重复步骤 3-5****。
    
然后配置自动授权，以便组的成员可自动分配 Office 365 和 EMS 订阅的许可证。
  
1. 在 Azure 门户中，单击“**Azure Active Directory”>“许可证”>“所有产品**”。
    
2. 在列表中，选择“Microsoft 365 企业版 E5”，然后单击“分配”********。
    
3. 在“**分配许可证**”边栏选项卡中，单击“**用户和组**”。
    
4. 在组列表中，选择以下各项：
    
  - 高层管理人员
    
  - 市场营销人员
    
5. 单击“**选择**”，然后单击“**分配**”。
    
6. 关闭浏览器中的 Azure 门户选项卡。
    
接下来，[连接到 Azure Active Directory PowerShell Graph 模块](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
填写组织名称、位置和公用密码并从 PowerShell 命令提示符或集成脚本环境 (ISE) 中运行以下命令，创建用户帐户并将其添加到相应的组：
  
```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> 此处使用公用密码旨在自动配置开发/测试环境，简化配置过程。 显然，对于生产订阅，这是非常不鼓励的。 
  
请按照以下步骤验证基于组的许可是否正常工作。
  
1. 在浏览器的“**Microsoft Office 主页**”标签页中，单击“**管理**”磁贴。
    
2. 在浏览器的新“**Microsoft 365 管理中心**”标签页中，单击“**用户**”。
    
3. 在用户列表中，单击“CEO”****。
    
4. 在列出“CEO”用户帐户属性的窗格中，验证已向其分配“Microsoft 365 企业版 E5”许可证（位于“产品许可证”中）************。
    
## <a name="phase-3-create-office-365-retention-labels"></a>阶段 3：创建 Office 365 保留标签

此阶段将针对基础 SharePoint 网站文档文件夹的不同安全级别创建保留标签。

1. 使用全局管理员帐户登录 [Microsoft 365 合规性门户](https://compliance.microsoft.com)。
    
2. 在浏览器的“**主页 - Microsoft 365 合规性**”选项卡中，单击“**分类 > 标签**”。
    
3. 单击“**保留标签 > 创建标签**”。
    
4. 在“命名标签”窗格上的“命名标签”中键入“敏感”，然后单击“下一步”****************。

5. 在“**文件计划描述符**”窗格中，单击“**下一步**”。
    
6. 在“**标签设置**”窗格中，根据需要将“**保留**”设置为“**开**”，然后单击“**下一步**”。
    
7. 在“**查看设置**”窗格中，单击“**创建标签**”。
    
8. 对名为“高度机密”的附加保留标签重复步骤3-7****。
    
9. 在“开始”>“标签”窗格中，单击“发布标签”********。
    
10. 在“选择要发布的标签”窗格中，单击“选择要发布的标签”********。
    
11. 在“选择标签”窗格中，单击“添加”并选择全部四个标签********。
    
12. 单击“完成”****。
    
13. 在“选择要发布的标签”窗格中，单击“下一步”********。
    
14. 在“**选择位置**”窗格中，单击“**下一步**”。
    
15. 在“**命名策略**”窗格中，在“**名称**”中键入“**示例组织**”，然后单击“**下一步**”。
    
16. 在“查看设置”**** 窗格中，单击“发布标签”****，然后单击“关闭”****。
    
## <a name="phase-4-create-your-teams"></a>阶段 4：创建团队

在此阶段中，可为你的示例组织创建和配置敏感和高度机密团队。

### <a name="sensitive-team-for-marketing-campaigns"></a>市场营销活动的敏感团队

为市场营销组成员创建敏感级别团队以共同协作处理持续市场营销活动：

1. 使用名称“市场营销活动”[创建新的私人团队](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)****。
2. 打开“市场营销活动”团队****。
3.  在团队的工具栏中，单击“文件”****。
4.  单击省略号，然后单击“在 SharePoint 中打开”****。
5.  在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”****。
6.  在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。
7.  在“共享权限”下方，选择“仅网站所有者可以共享文件、文件夹和网站”，然后单击“保存”************。

接下来，针对敏感标签配置基础市场营销活动 SharePoint 网站的文档文件夹。

1.  在浏览器的“市场营销活动 - 主页”选项卡中，单击“文档”********。
2.  单击设置图标，然后单击“库设置”****。
3.  在“权限和管理”下，单击“向此库中的项应用标签”********。
4.  在“**设置 - 应用标签**”中，选择“**敏感**”，然后单击“**保存**”。 

接下来，配置数据丢失防护 (DLP) 策略，以便在用户共享关于含敏感标签的基础 SharePoint 网站（包括组织外的营销活动网站）的文档时进行通知。

1. 使用全局管理员帐户登录 [Microsoft 365 合规性门户](https://compliance.microsoft.com/)。
    
2. 在浏览器的新“**Microsoft 365 合规**”标签页中，单击“**策略 > 数据丢失防护**”。
    
3. 在“**主页 > 数据丢失防护**”窗格中，单击“**创建策略**”。
    
4. 在“从模板开始或创建自定义策略”**** 窗格中，单击“自定义”****，然后单击“下一步”****。
    
5. 在“命名策略”**** 窗格中，在“名称”中键入“敏感标签 SharePoint 网站”********，然后单击“下一步”****。
    
6. 在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”************。
    
7. 在位置列表中，禁用“**Exchange 电子邮件**”、“**OneDrive 帐户**”和“**Teams 聊天和频道消息**”，然后单击“**下一步**”。
    
8. 在“**自定义要保护的内容类型**”窗格中，单击“**编辑**”。
    
9. 在“**选择要保护的内容类型**”窗格中，单击下拉框中的“**添加**”，然后单击“**保留标签**”。
    
10. 在“**保留标签**”窗格中，单击“**添加**”，选择“**敏感**”标签，然后依次单击“**添加**”和“**完成**”。
    
11. 在“选择要保护的内容类型”窗格中，单击“保存”********。
    
12. 在“**自定义要保护的敏感信息类型**”窗格中，单击“**下一步**”。

13. 在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”********。
    
14. 在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”********。
    
15. 在文本框中，键入或粘贴以下内容：
    
  - 要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。
    
16. 单击“确定”。
    
17. 在“如果检测到敏感信息，希望采取什么操作?”**** 窗格中，单击“下一步”****。
    
18. 在“是否希望立即启用策略或先进行测试?”**** 窗格中，单击“是，立即启用”****，然后单击“下一步”****。
    
19. 在“查看设置”**** 窗格中，单击“创建”****，然后单击“关闭”****。

下面是市场营销活动团队的配置结果。

![市场营销活动团队的配置。](../../media/sensitive-team-config-dev-test.png)
  
### <a name="company-strategy-team-site"></a>公司战略团队网站

若要为高级领导团队成员创建高度机密级别的团队以便协作处理公司战略，请执行以下操作：

1. 使用名称“公司战略”[创建新的私人团队](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)****。
2. 打开“公司战略”团队****。
3.  在团队的工具栏中，单击“文件”****。
4.  单击省略号，然后单击“在 SharePoint 中打开”****。
5.  在基础 SharePoint 网站的工具栏中，依次单击设置图标和“网站权限”****。
6.  在“**网站权限**”窗格的“**共享设置**”下方，单击“**更改共享设置**”。
7.  在“**共享权限**”下方，选择“**仅网站所有者可以共享文件、文件夹和网站**”。
8.  关闭“**允许访问请求**”，然后单击“**保存**”。

接下来，针对高度机密标签配置基础公司战略 SharePoint 网站的文档文件夹。

1.  在浏览器的“公司战略 - 主页”选项卡中，单击“文档”********。
2.  单击设置图标，然后单击“库设置”****。
3.  在“权限和管理”下，单击“向此库中的项应用标签”********。
4.  在“**设置 - 应用标签**”中，选择“**高度机密**”，然后单击“**保存**”。 

接下来，配置 DLP 策略，当用户在具有“高度机密”标签的基础 SharePoint 网站（包括组织外的公司战略网站）上共享文档时，该策略会阻止用户。
  
1. 使用全局管理员登录 [Microsoft 365 合规性门户](https://compliance.microsoft.com/)。
    
2. 在浏览器的新“**Microsoft 365 合规**”标签页中，单击“**策略 > 数据丢失防护**”。
    
3. 在“**主页 > 数据丢失防护**”窗格中，单击“**创建策略**”。
    
4. 在“从模板开始或创建自定义策略”**** 窗格中，单击“自定义”****，然后单击“下一步”****。
    
5. 在“命名策略”**** 窗格中，在“名称”中键入“高度机密标签 SharePoint 网站”********，然后单击“下一步”****。
    
6. 在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”************。
    
7. 在位置列表中，禁用“**Exchange 电子邮件**”、“**OneDrive 帐户**”和“**Teams 聊天和频道消息**”，然后单击“**下一步**”。
    
8. 在“**自定义要保护的内容类型**”窗格中，单击“**编辑**”。
    
9. 在“**选择要保护的内容类型**”窗格中，单击下拉框中的“**添加**”，然后单击“**保留标签**”。
    
10. 在“**保留标签**”窗格中，单击“**添加**”，选择“**高度机密**”标签，然后依次单击“**添加**”和“**完成**”。
    
11. 在“选择要保护的内容类型”窗格中，单击“保存”********。
    
12. 在“**自定义要保护的敏感信息类型**”窗格中，单击“**下一步**”。

13. 在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”********。
    
14. 在“自定义策略提示和电子邮件通知”窗格中，单击“自定义策略提示文本”********。
    
15. 在文本框中，键入或粘贴以下内容：
    
  - 要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。
    
16. 单击“确定”。
    
17. 在“是否希望立即启用策略或先进行测试?”**** 窗格中，单击“是，立即启用”****，然后单击“下一步”****。

18. 在“是否希望立即启用策略或先进行测试?”**** 窗格中，单击“是，立即启用”****，然后单击“下一步”****。
    
19. 在“查看设置”**** 窗格中，单击“创建”****，然后单击“关闭”****。

按照[这些说明](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)，使用以下设置配置敏感度标签：

- 标签名称是“公司战略”
- 启用加密
- 公司战略组具有共同创作权限

创建后，发布新标签。 如果以公司战略组成员身份登录，将在 Word、Excel 和 PowerPoint 的“开始”工具栏中的“敏感度”选项中看到新的标签。 从“敏感度”选项中选择“公司战略”标签，将标签分配给文件。

下面是公司战略团队的配置结果。

![公司战略团队的配置。](../../media/highlyconfidential-team-config-dev-test.png) 

基础公司战略 SharePoint 网站的“文档”部分中的文件被分配有高度机密保留标签，并遵循配置的 DLP 策略。 还可以为文件分配“公司战略”敏感度标签。    
  
## <a name="next-step"></a>后续步骤

如果已准备好进行生产部署，请参阅[保护 Microsoft Teams 中的文件](secure-files-in-teams.md)，了解详细信息，获取分步部署文章的链接。
  
## <a name="see-also"></a>另请参阅

[云应用和混合解决方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
