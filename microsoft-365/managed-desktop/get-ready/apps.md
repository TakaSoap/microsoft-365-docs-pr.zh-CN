---
title: Microsoft 托管桌面中的应用程序
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a24212cf69df50d00a32f17e8daf1939657dd602
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632847"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft 托管桌面中的应用程序

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>应用程序通常

Microsoft 包括一些关键应用，以及 Microsoft 365 E3 或 E5 许可证需要参与 Microsoft 托管桌面。 但是，即使我们提供这些应用，仍需要完成一些责任和操作。

您还可以通过公司门户或所需的后台安装将其他非 Microsoft 应用程序部署到最终用户，以使用 Microsoft Intune 的部署管道进行自助服务。 如果你有专业技能，你可以自行迁移你需要的应用程序;或者，Microsoft 咨询服务（MCS）或非 Microsoft 供应商将非常乐意帮助你进行打包和迁移项目。 有关使用 MCS 的详细信息，请参阅使用[Microsoft 咨询服务](apps-MCS.md)。


## <a name="apps-provided-by-microsoft"></a>Microsoft 提供的应用程序

包含在 Microsoft 托管桌面许可证中，适用于企业标准套件（Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business 和 OneNote）中的 Microsoft 365 应用中的应用程序的64位版本。默认情况下，*不*包含即点即用版本的 Microsoft Project 和 Visio，但您可以请求添加它们。 有关这些应用程序的详细信息，请参阅[在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft 为支持我们提供的应用程序所做的操作

Microsoft 将为适用于企业应用的包含 Microsoft 365 应用程序的部署、更新和支持提供完整服务。 即点即用版本的 Microsoft Project 和 Visio 在默认情况下*不*包括在内，但 Microsoft 托管桌面将提供部署组，使您的 IT 管理员能够管理许可证并为您的组织适当地部署这些应用程序。 Microsoft 将通过 Microsoft 托管桌面支持频道支持这些应用程序的最终用户。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>为支持我们提供的应用程序所需的操作

对于这些应用程序，仍需要执行某些操作：

- **分配许可证**-您负责为 Microsoft 365 应用程序的最终用户获取和分配适当的许可证。
- **将用户添加到安全组**-如果你使用的是 Microsoft Project 或 VISIO，IT 管理员必须将这些用户添加到相应的部署组。 IT 管理员还负责从这些用户那里回收许可证（如果他们离开公司）。
- **部署 microsoft 365 加载项**-如果您需要任何适用于企业应用程序的 Microsoft 365 应用程序的任何加载项，请像在任何其他 Windows 32 应用中集中部署它们。 

## <a name="apps-you-provide"></a>你提供的应用

当然，您可能需要许多其他应用程序来实现业务运营。 仅可使用 Microsoft Intune 的部署管道将这些这些部署到 Microsoft 托管桌面设备。 如果应用程序需要，可以让供应商打包它们（可能是非 Microsoft 供应商或 Microsoft 咨询服务（MCS）），或者如果你有这种方法，则可以自行打包。 然后，将这些程序包添加到 Microsoft 托管桌面门户，并将其分配给 Azure Active Directory 组以触发部署。 

如果你当前使用 Microsoft 终结点配置管理器部署应用，Microsoft 托管桌面可以向你提供一个查询，用于评估你的应用程序，并发现哪些应用程序可以迁移到 Microsoft Intune，以及哪些可能需要进行一些调整。


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>准备您自己的应用程序以包含在 Microsoft 托管桌面中
查看您的应用程序，检查：

- 不允许任何应用程序，也不具有限制的行为，如[Microsoft 托管桌面应用程序要求](https://aka.ms/app-req)中所述。
- 应用必须准备好由 Microsoft Intune 进行管理。 有关此信息的详细信息，请参阅[使用 Microsoft intune 的 Windows 10 应用程序部署](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)和[向 Microsoft intune 添加应用程序](https://docs.microsoft.com/intune/apps-add)。
- 其他预打包要求，例如提供许可证密钥、许可条款协议和预设置服务器连接。

### <a name="decide-how-to-package-apps"></a>决定如何打包应用程序

某些独立软件供应商可能需要先打包应用程序，然后再进行集中部署。 "打包" 意味着应用程序的安装程序配置了诸如许可证密钥、远程服务器位置或桌面快捷方式之类的设置，以便可以在后台安装应用程序。

有三个选项可用于获取打包的应用程序： 


- 您可以自己打包应用程序
- 您可以使用非 Microsoft 供应商
- 你可以与 MCS 接洽以打包你的应用。 与你的 Microsoft 帐户代表合作。 有关更多详细信息，请参阅使用[Microsoft 咨询服务](apps-MCS.md)。







## <a name="deploying-apps"></a>部署应用程序

无论使用哪种方法来获取打包的应用程序，完成后，都可以按照 "[将应用程序部署到 Microsoft 托管桌面设备](../get-started/deploy-apps.md)" 中的步骤进行操作。


