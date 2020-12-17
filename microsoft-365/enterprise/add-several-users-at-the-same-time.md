---
title: 同时将多个用户添加到 Microsoft 365 - 管理员帮助
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
ms.assetid: 1f5767ed-e717-4f24-969c-6ea9d412ca88
description: '了解如何从电子表格或其他 CSV 格式文件的列表向 Microsoft 365 商业版添加多个用户。 观看 YouTube 上说明如何向 Microsoft 365 添加帐户的视频。 在此过程结束时，每个拥有帐户的用户都将拥有一个 Microsoft 365 邮箱。 '
ms.openlocfilehash: 71e1d1f9261fc58e9f49fac5050e07fd7b8839e3
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698263"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a>同时将多个用户添加到 Microsoft 365 - 管理员帮助

团队中的每个人都需要一个用户帐户，然后才能登录和访问 Microsoft 365 服务，如电子邮件和 Office。 如果您有很多用户，则可以通过 Excel 电子表格或其他以 CSV 格式保存的文件一次添加其帐户。 [不确定什么是 CSV 格式？](add-several-users-at-the-same-time.md#__toc316652088)
  
> [!NOTE] 
> 如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心中添加多个用户

1. 使用工作或学校帐户登录 Microsoft 365。 
    
2. 在管理中心中，选择 **"用户** \> **活动用户"。**

3. 选择 **"添加多个用户"。**

4. 在" **导入多个用户** "面板上，可以选择下载包含或不填充示例数据的示例 CSV 文件。 
    
    电子表格需要包含与示例一完全相同的列标题 (用户名、名字等) 。 如果使用模板，在文本编辑工具（如记事本）中打开它，并考虑将第 1 行的所有数据都单独保留，并且仅输入行 2 和下面的数据。 
    
    电子表格还需要包括用户名值，例如 (bob@contoso.com) 和 显示名称 (Bob Kelly) for each user。 
    
  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. 在框中输入文件路径，**或选择"** 浏览"浏览到 CSV 文件位置，然后选择"**验证"。**
  
    如果文件有问题，则问题将显示在面板中。 您还可以下载日志文件。
    
5. 在 **"设置用户选项** "对话框中，可以设置登录状态并选择将分配给所有用户的产品许可证。 
    
6. 在"查看结果"对话框中，可以选择将结果发送给您自己或其他用户 (密码将为纯文本) 并且可以查看已创建的用户数，以及是否需要购买更多许可证以分配给一些新用户。 

## <a name="next-steps"></a>后续步骤
<a name="bk_preview"> </a>

- 现在，这些用户拥有帐户，他们需要在电脑或 Mac 上下载并安装或重新安装[Microsoft 365 或 Office 2016。](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) 团队中每个人都可以在最多 5 台电脑或 Mac 上安装 Microsoft 365。 
    
- 每个人还可以在最多 5 台平板电脑和 5 部手机上的移动设备上设置 [Office](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) 应用和电子邮件，如 iPhone、iPad 和 Android 手机和平板电脑。 这样，他们可以从任何位置编辑 Office 文件。 
    
    有关安装步骤的端到端列表，请参阅"设置 [Microsoft 365](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) 商业版"。 
    
## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a>有关如何将用户添加到 Microsoft 365 中详细信息
<a name="bk_preview"> </a>

### <a name="not-sure-what-csv-format-is"></a>不确定什么是 CSV 格式？
<a name="__toc316652088"> </a>

CSV 文件是包含逗号分隔值的文件。 可以使用任何文本编辑器或电子表格程序（如 Excel）创建或编辑此类文件。
  
您可以下载 [此示例电子表格](https://www.microsoft.com/download/details.aspx?id=45485) 作为起点。 请记住，Microsoft 365 需要第一行中的列标题，因此不要将它们替换为其他标题。 
  
使用新名称保存文件，并指定 CSV 格式。
  
![如何以 CSV 格式将文件保存为 Excel 的图像](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
保存文件时，如果以 CSV 格式保存文件，则可能会提示工作簿中的某些功能将丢失。 这没有问题。 单击" **是**"即可继续。 
  
![从 Excel 获取的提示图片，询问是否确实要将文件保存为 CSV 格式](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a>设置电子表格格式的提示
<a name="__toc314595848"> </a>

- **是否需要与示例电子表格中相同的列标题？** 是。 示例电子表格包含第一行中的列标题。 这些标题是必需的。 对于要添加到 Microsoft 365 的每个用户，在标题下创建一行。 如果添加、更改或删除任何列标题，Microsoft 365 可能无法从文件中的信息创建用户。 
    
- **如果我没有每个用户所需的全部信息，应该如何操作？** 用户名和显示名称是必需的，如果没有此信息，则不能添加新用户。 如果没有其他一些信息（如传真），可以使用空格加逗号来指示字段应保留为空。 
    
- **电子表格可以小到大？** 电子表格必须至少包含两行。 一个列标题用于 (数据列标签) 列标题，另一个列标题用于用户。 行数不能超过 251。 如果需要导入 250 多个用户，可以创建多个电子表格。 
    
- **我可以使用哪些语言？** 创建电子表格时，可以使用任何语言或字符输入用户数据列标签，但不得更改标签的顺序，如示例中所示。 然后，可以使用任何语言或字符将条目输入字段，以 Unicode 或 UTF-8 格式保存文件。 
    
- **如果我添加来自不同国家/地区的用户，该做什么？** 为每个区域创建单独的电子表格。 你需要逐步完成批量添加用户向导，其中每个电子表格都提供一个包含于你正在处理的文件的所有用户的位置。 
    
- **我可以使用的字符数是否有限制？** 下表显示了示例电子表格中的用户数据列标签和每个标签的最大字符长度。 
    
|**用户数据列标签**|**最大字符长度**|
|:-----|:-----|
|用户名 (必需)   <br/> |79，包括 at 符号 (@) ，格式为 \<extension\> name@domain。 用户的别名不能超过 50 个字符，并且域名不能超过 48 个字符。  <br/> |
|名字  <br/> |64  <br/> |
|姓氏  <br/> |64  <br/> |
|显示名称 (是必需的)   <br/> |256  <br/> |
|职务  <br/> |64  <br/> |
|Department  <br/> |64  <br/> |
|Office 号码  <br/> |128  <br/> |
|办公室电话  <br/> |64  <br/> |
|Mobile Phone － 移动电话  <br/> |64  <br/> |
|Fax  <br/> |64  <br/> |
|地址  <br/> |1023  <br/> |
|市/县  <br/> |128  <br/> |
|省/自治区/直辖市  <br/> |128  <br/> |
|邮政编码  <br/> |40  <br/> |
|国家或地区  <br/> |128  <br/> |
   
### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a>向 Microsoft 365 添加用户时仍有问题？

- **仔细检查电子表格的格式是否正确。** 检查列标题以确保它们与示例文件中的标题匹配。 确保遵循字符长度规则，并且每个字段用逗号分隔。 
    
- **如果在 Microsoft 365 中看不到新用户，请等待几分钟。** 可能需要一点时间更改才能在 Microsoft 365 中跨所有服务。 
    
## <a name="related-articles"></a>相关文章

[将用户单独或批量添加到 Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/add-users)




