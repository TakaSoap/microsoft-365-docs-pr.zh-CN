---
title: 将外部联系人批量导入Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
ms.custom: admindeeplinkEXCHANGE
description: 了解管理员如何使用 Exchange Online PowerShell 和 CSV 文件将外部联系人批量导入到全局地址列表。
ms.openlocfilehash: fbb2d9bb93d9275e662872d945254d6bf27deb92
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423907"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>将外部联系人批量导入Exchange Online

**本文适用于管理员。您尝试将联系人导入到您自己的邮箱吗？请参阅 [将联系人导入Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
贵公司是否有大量要包括在共享通讯簿中的现有业务联系人 (在通讯簿中也称为全局) 列表Exchange Online？ 您是否希望将外部联系人添加为通讯组的成员，就像可以与公司内部的用户一样？ 如果是这样，可以使用 PowerShell Exchange Online CSV (逗号分隔值) 文件将外部联系人批量导入Exchange Online。 此过程分三步完成：
  
[步骤 1：创建包含有关外部联系人信息的 CSV 文件](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[步骤 2：使用 PowerShell 创建外部联系人](#step-2-create-the-external-contacts-with-powershell) 

[步骤 3：向外部联系人的属性添加信息](#step-3-add-information-to-the-properties-of-the-external-contacts)

完成这些步骤以导入联系人后，可以执行以下附加任务：
  
- [添加更多外部联系人](#add-more-external-contacts)
  
- [从共享通讯簿中隐藏外部联系人](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>步骤 1：创建包含有关外部联系人信息的 CSV 文件

第一步是创建一个 CSV 文件，其中包含有关要导入到外部联系人Exchange Online。 
  
1. 将以下文本复制到记事本中的文本文件中，然后使用文件名后缀 .csv;例如，ExternalContacts.csv。
    
    > [!TIP]
    > 如果你的语言包含特殊字符 (例如瑞典语) 在将文件保存在记事本中时，使用 UTF-8 或其他 Unicode 编码保存 CSV 文件。  
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    CSV 文件的第一行（即标题行）列出了在将联系人导入到网站时可以使用Exchange Online。 每个属性名称用逗号分隔。 标题行下的每一行代表用于导入单个外部联系人的属性值。 
    
    > [!NOTE]
    > 此文本包含您可以删除的示例数据。 但请勿删除或更改第一个 (标题) 行。 它包含外部联系人的所有属性。 
  
2. 在文件Microsoft Excel CSV 文件以编辑 CSV 文件，因为使用 Excel 编辑 CSV 文件要容易得多。
    
3. 为要导入联系人的每个联系人创建一Exchange Online。 填充尽可能多的单元格。 此信息将显示在每个联系人的共享通讯簿中。 
    
    > [!IMPORTANT]
    >  以下属性 (创建外部联系人时需要以下属性，这些属性是标题行) 中的前四项，并且必须在 CSV 文件中填充 **：ExternalEmailAddress、Name、FirstName** 和 **LastName**。  在步骤 2 中运行的 PowerShell 命令将使用这些属性的值来创建联系人。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>步骤 2：使用 PowerShell 创建外部联系人

下一步是使用在步骤 1 和 PowerShell 中创建的 CSV 文件将 CSV 文件中列出的外部联系人批量导入到Exchange Online。 
  
1.  连接 PowerShell Exchange Online组织。 有关分步说明，请参阅[连接 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 在连接到 PowerShell 时，请务必使用全局管理员帐户的Exchange Online密码。 
    
2. 将 PowerShell 连接到 Exchange Online，转到步骤 1 中保存 CSV 文件的桌面文件夹;例如 `C:\Users\Administrator\desktop` 。
    
3. 运行以下命令以创建外部联系人：

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    创建新联系人可能需要一段时间，具体取决于要导入的联系人数。 命令运行完毕后，PowerShell 将显示已创建的新联系人的列表。 
    
4. 若要查看新的外部联系人，请转到 EAC Exchange管理中心 () ，然后单击"**收件人** \> <a href="https://go.microsoft.com/fwlink/?linkid=2182970" target="_blank">**联系人"。**</a> 
    
    > [!TIP]
    > 有关连接到 EAC 的说明，请参阅 Exchange[中的管理Exchange Online。](/exchange/exchange-admin-center) 
  
5. 如有必要，请单击 **"刷新** "以更新列表并查看已导入的外部联系人。 
    
    导入的联系人将显示在共享通讯簿中的 Outlook 和 Outlook 网页版。
    
    > [!NOTE]
    > 您还可以通过访问"用户联系人"查看Microsoft 365 管理中心联系人 \> **。** 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>步骤 3：向外部联系人的属性添加信息

在步骤 2 中运行命令后，将创建外部联系人，但它们不包含任何联系人或组织信息，这些信息来自 CSV 文件中大多数单元格的信息。 这是因为在创建新的外部联系人时，只会填充所需的属性。 如果您未在 CSV 文件中填充所有信息，请不要担心。 如果不存在，则不添加它。
  
1.  连接 PowerShell Exchange Online组织。 有关分步说明，请参阅[连接 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
    
2. 转到步骤 1 中保存 CSV 文件的桌面文件夹;例如， `C:\Users\Administrator\desktop` 。
    
3. 运行以下两个命令，将 CSV 文件的其他属性添加到在步骤 2 中创建的外部联系人。
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _Manager_ 参数可能有问题。 如果 CSV 文件中单元格为空，将发生错误，并且不会向联系人添加任何属性信息。 如果不需要指定管理器，只需从以前的  ` -Manager $_.Manager ` PowerShell 命令中删除。 
  
    同样，可能需要一段时间来更新联系人，具体取决于在步骤 1 中导入的联系人数。 
    
4. 若要验证属性已添加到联系人： 
    
1. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center，</a>go to **Recipients** \> **Contacts**.
    
2. 单击联系人，然后单击" **编辑编辑** ![ "图标。](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 显示联系人的属性。 
    
就是这么简单。 用户可以在通讯簿和通讯簿中查看联系人Outlook Outlook 网页版。
  
## <a name="add-more-external-contacts"></a>添加更多外部联系人

可以重复步骤 1 到步骤 3，以在 Exchange Online 中添加新的外部Exchange Online。 你或公司中的用户只需在 CSV 文件中为新联系人添加一个新行。 然后，可以运行步骤 2 和步骤 3 中的 PowerShell 命令，以创建信息并将其添加到新联系人。
  
> [!NOTE]
> 运行命令创建新联系人时，可能会看到一条错误消息，指出先前创建的联系人已经存在。 但会创建添加到 CSV 文件的任何新联系人。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>从共享通讯簿中隐藏外部>

某些公司只能使用外部联系人，以便可以添加为通讯组的成员。 在此方案中，他们可能想要从共享通讯簿中隐藏外部联系人。 操作步骤如下：
  
1.  连接 PowerShell Exchange Online组织。 有关分步说明，请参阅[连接 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。
    
2. 若要隐藏单个外部联系人，请运行以下命令。
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    例如，若要从共享通讯簿中隐藏 Pilar Pinilla，请运行以下命令：

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. 若要从共享通讯簿中隐藏所有外部联系人，请运行以下命令：

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

隐藏外部联系人后，外部联系人不会显示在共享通讯簿中，但您仍可以将它们添加为通讯组的成员。