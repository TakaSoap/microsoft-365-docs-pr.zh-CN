---
title: 使用 PowerShell 管理 Skype for Business Online 策略
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 摘要：使用 PowerShell 通过策略Skype for Business Online 用户帐户属性。
ms.openlocfilehash: 674ea6daba498279537f7c302f4bf4d791ee00f5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189077"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>使用 PowerShell 管理 Skype for Business Online 策略

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

若要管理 Skype for Business Online 用户帐户的许多属性，必须使用 PowerShell for Microsoft 365 将其指定为策略Microsoft 365。
  
## <a name="before-you-begin"></a>准备工作

使用这些说明设置以运行命令 (跳过已完成以下) ：

  > [!Note]
  > Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果你使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。

1. 安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 开启 Windows PowerShell 命令提示符并运行以下命令： 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   系统提示时，输入 Skype for Business Online 管理员帐户名称和密码。
    
## <a name="manage-user-account-policies"></a>管理用户帐户策略

许多 Skype for Business Online 用户帐户属性都是使用策略配置的。 策略只是一组可应用于一个或多个用户的设置。 若要了解策略的配置方式，您可以为 FederationAndPICDefault 策略运行此示例命令：
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

反过来，应返回类似以下内容：
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

本示例中，此策略中的值确定在与联盟用户通信时，使用可以或不能执行哪些用途。 例如，EnableOutsideAccess 属性必须设置为 True，用户才能与组织外部的用户通信。 请注意，此属性不会显示在Microsoft 365 管理中心。 而是根据你做出的其他选择自动将该属性设置为 True 或 False。 其他两个感兴趣的属性是：
  
- **EnableFederationAccess** 指示用户是否可以与联合域的用户通信。
    
- **EnablePublicCloudAccess** 指示用户是否可以与 Windows Live 用户通信。
    
因此，不要直接更改用户帐户上与联合身份验证相关的属性 (例如 **Set-CsUser -EnableFederationAccess $True) 。** 而是为帐户分配一个预配置了所需属性值的外部访问策略。 如果我们希望用户能够与联盟用户和 Windows Live 用户通信，则必须为用户帐户分配允许这些类型的通信的策略。
  
如果您想了解某人是否可以与组织外部的用户通信，您必须：
  
- 确定为此用户分配的是哪种外部访问策略。
    
- 确定此策略允许的许可范围。
    
例如，可以使用此命令进行此操作：
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

此命令查找分配给用户的策略，然后查找该策略中启用或禁用的功能。
  
若要Skype for Business PowerShell 管理联机策略，请参阅以下 cmdlet：

- [客户端策略](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [会议策略](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [移动策略](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [联机语音邮件策略](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [语音路由策略](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> "Skype for Business Online 拨号计划"是除名称以外的所有方面的策略。 选择名称"拨号计划"，而不是"拨号策略"，以提供与 Office Communications Server 和 Exchange 的向后Exchange。 
  
例如，若要查看所有可供使用的语音策略，请运行以下命令：
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> 将返回所有可用的语音策略的列表。 但请记住，并非所有策略都可以分配给所有用户。 这是因为涉及许可和地理位置的各种限制。  (所谓的"[使用位置"。](/previous-versions/azure/dn194136(v=azure.100))) 如果您想要了解可分配给特定用户的外部访问策略和会议策略，请使用以下类似命令： 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

ApplicableTo 参数可将返回的数据限制为可分配到特定用户的策略（例如，Alex Darrow）。根据不同的授权和使用位置限制，可能会代表所有可用策略的子集。 
  
在某些情况下，策略的属性不用于Microsoft 365，而其他属性只能由 Microsoft 支持人员进行管理。 
  
使用 Skype for Business Online，用户必须由某种策略进行管理。 如果与策略相关的有效属性为空，则意味着相关用户由全局策略管理，全局策略是自动应用于用户的策略，除非专门为其分配每用户策略。 因为我们未看到为用户帐户列出的客户端策略，所以它由全局策略管理。 可以使用此命令确定全局客户端策略：
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>另请参阅

[使用 PowerShell 管理 Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[使用 PowerShell 管理 Microsoft 365](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[PowerShell for Microsoft 365 入门](getting-started-with-microsoft-365-powershell.md)