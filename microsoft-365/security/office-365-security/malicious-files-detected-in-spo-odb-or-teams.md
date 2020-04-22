---
title: 查看有关在 SharePoint、OneDrive 或 Microsoft 团队中检测到的恶意文件的信息
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: 了解在何处可以查看有关在 SharePoint、OneDrive 或团队中检测到的恶意文件的信息，以及如何对这些文件执行操作。
ms.openlocfilehash: 95f497c5be16d1ba1d4fa9fc57f0dd9650450414
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635396"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>查看有关在 SharePoint、OneDrive 或 Microsoft 团队中检测到的恶意文件的信息

[适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](atp-for-spo-odb-and-teams.md)可保护您的组织免受文档库和工作组网站中的恶意文件的攻击。 检测到恶意文件时，将阻止该文件，以便在组织的安全团队执行进一步操作之前，任何人都无法打开、复制、移动或共享该文件。 阅读本文，了解如何查看有关检测到的文件以及要执行的操作的信息。 

若要执行本文中所述的任务，您必须具有[针对安全&amp;合规中心](permissions-in-the-security-and-compliance-center.md)的必要权限。 
  
## <a name="view-reports-with-information-about-detected-files"></a>查看包含检测到的文件的相关信息的报告

若要查看 Office 365 ATP 检测到的文件的状态和详细信息，可以使用威胁防护状态报告。
  
1. 在 "[安全&amp;合规性中心](https://protection.office.com)" 中，选择 "**报告** \> "**仪表板** \> **威胁防护状态**。
    
2. 在报表的右上角，选择 "**查看详细信息表**"。
    
3. 查看在报告中检测到的文件的列表。
    
4. 选择列表中的项目以查看详细信息，包括执行的操作、文件名、文件路径等。
    
5. 选择 "**高级分析**" 选项卡以查看信息，如观察到的行为和分析详细信息。 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>查看隔离区中的文件并对其执行操作

1. 在 "安全&amp;合规性中心" 中，选择 "**威胁管理** \> **检查** \> **隔离**"。 （你也可以直接转到[https://protection.office.com/quarantine](https://protection.office.com/quarantine)。）
    
2. 在左上角，将下拉菜单从**电子邮件**更改为**文件**。 如果结果列表中包含过多项目，请使用**筛选**功能缩小选定范围。
    
3. 选择列表中的某一项，以查看详细信息，包括文件的 URL。
    
4. 选择可用操作。
    
    - 选择 "**释放文件**" 以取消阻止该文件。 

      选择 "**将报告发送给 microsoft** " 以将该文件报告为 "误报到 microsoft"。 

    - 选择 "**下载文件**" 以进一步调查文件。 

    - 选择 "**从隔离区删除**" 以从隔离项目列表中删除该文件。 如果选择此选项，则还必须在 SharePoint Online、OneDrive for Business 或 Microsoft 团队中从其各自的库中删除文件。 此选项不会取消阻止打开或共享文件。 
    
5. 选择 "**关闭**" 以关闭所选项目的详细信息。 
  
  

