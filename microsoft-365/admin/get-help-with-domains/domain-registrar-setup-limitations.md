---
title: 具有设置限制的域注册机构
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- MET150
ROBOTS: NOINDEX
description: 某些域注册机构提供有限的服务，这意味着并非所有 Microsoft 功能都适用于每个域。
ms.openlocfilehash: 2d192f03c5a586e4355c1f9a08d312a07af3d501
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60164725"
---
# <a name="domain-registrars-with-setup-limitations"></a>具有设置限制的域注册机构

[在 DNSMadeEasy 为 Microsoft 创建 DNS 记录](#create-dns-records-at-dnsmadeeasy-for-microsoft)\
[在 easyDNS 为 Microsoft 创建 DNS 记录](#create-dns-records-at-easydns-for-microsoft)\
[在 Freenom 为 Microsoft 创建 DNS 记录](#create-dns-records-at-freenom-for-microsoft)\
[在 MyDomain 为 Microsoft 创建 DNS 记录](#create-dns-records-at-mydomain-for-microsoft)\
[使用基于 Windows 的 DNS 为 Microsoft 创建 DNS 记录](#create-dns-records-for-microsoft-using-windows-based-dns)\
[当域由 Google (eNom) 托管时，创建 DNS 记录](#create-dns-records-when-your-domain-is-managed-by-google-enom)\
[在 1&1 IONOS 为 Microsoft 创建 DNS 记录](#create-dns-records-at-11-ionos-for-microsoft)

某些域注册机构具有重大的服务限制，这意味着并非所有 Microsoft 功能都适用于每个域。 本文介绍了某些注册机构的特定限制。 

## <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a>在 DNSMadeEasy 处为 Microsoft 创建 DNS 记录

对于 DNSMadeEasy 帐户，添加的域是从单独的域注册机构处购买的。 DNSMadeEasy 不提供域注册服务。 如果能够在 DNSMadeEasy 处登录并创建 DNS 记录，便可证明拥有所有权。

## <a name="create-dns-records-at-easydns-for-microsoft"></a>在 easyDNS 中为 Microsoft 创建 DNS 记录

SRV 记录当前在任何 easyDNS 服务包下都不可用。 可能需要升级到具有 easyDNS 的更高服务级别才能添加 Teams 所需的 SRV 记录。

## <a name="create-dns-records-at-freenom-for-microsoft"></a>在 Freenom for Microsoft 创建 DNS 记录

Freenom 网站不支持添加 SRV 记录，这意味着多个 Teams 和电子邮件功能将不起作用。无论你使用哪种 Microsoft 计划，都存在重大的服务限制，你可能希望切换到其他 DNS 托管提供商。

## <a name="create-dns-records-at-mydomain-for-microsoft"></a>在 MyDomain 处为 Microsoft 创建 DNS 记录

MyDomain 网站不支持 SRV 记录，这意味着多个 Teams 和电子邮件功能将不可用。无论使用哪个 Microsoft 计划，如果在 MyDomain 处管理 DNS 记录，则有较大的服务限制，用户可能会想要切换为其他 DNS 托管提供者。

## <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>使用基于 Windows 的 DNS 为 Microsoft 创建 DNS 记录

转到包含你的域的 DNS 记录页面。 如果在 Windows Server 2008 中工作，请转到“**开始**”，“**运行**”。 如果在 Windows Server 2012 中工作，请按 **Windows 徽标键** 和 **r**。 键入 **dnsmgmnt.msc**，然后选择 **确定**。 在 DNS 管理器中，展开“**DNS 服务器名称**”，“**正向查找区域**”。 选择域。 现在已准备好创建 DNS 记录。

## <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>当域由 Google (Go Daddy) 托管时，创建 DNS 记录

如果在注册 Google Apps for Work 帐户时通过 Google 购买了域，则 DNS 记录由 Google 管理，但注册到 eNom。可以通过 Google 域页面访问 eNom 并创建 DNS。

## <a name="create-dns-records-at-11-ionos-for-microsoft"></a>在 1&1 IONOS 为 Microsoft 创建 DNS 记录

1&1 IONOS 不允许一个域同时具有 MX 记录和顶级自动发现 CNAME 记录。 这将限制为 Microsoft 配置 Exchange Online 的方式。 有一个解决方法，但是建议仅当已体验过在 1&1 IONOS 创建子域时，才使用这个方法。

如果忽视此服务限制，选择在 1&1 IONOS 管理自己的 Microsoft DNS 记录，请按照本文中的步骤验证域并为电子邮件和 Skype for Business Online 等设置 DNS 记录。

1&1 IONOS 需要一种解决方法，以便可将 MX 记录与 Microsoft 电子邮件服务所需的 CNAME 记录一并使用。 此解决方法需要在 1&1 IONOS 创建一组子域并将其分配到 CNAME 记录。

> [!NOTE]
> 在开始此过程之前，请确保具有至少两个可用子域。 建议仅当已体验过在 1&1 IONOS 创建子域时，才使用此解决方案。

### <a name="basic-cname-records"></a>基本 CNAME 记录

1.  若要开始，请在 1&1 IONOS 转到域页面。 系统将会提示你登录。

1.  选择 **管理域**。

1.  在“域中心”页面中，找到要更新的域，然后选择“**管理子域**”。 现在，你将创建两个子域并为每个子域设置一个 **Alias** 值（这是必需的，因为 1&1 IONOS 仅支持一个顶级 CNAME 记录，但 Microsoft 需要多个 CNAME 记录。）

1.  首先，将创建自动发现子域。 在“**子域概述**”部分中，选择“**创建子域**”。

1.  在新子域的“**创建子域**”框中，只键入或复制并粘贴下表中的“**创建​​子域**”值。（将在后一步中添加“**别名**”值。）

    |创建子域|别名|
    |:----|:----|
    |自动发现|autodiscover.outlook.com|

1.  选择 **创建子域**。

1.  在“**子域概述**”部分中，找到刚才创建的“自动发现”子域，然后选择该子域的“面板(v)”控件。

1.  在“**子域设置**”区域中，选择“**编辑 DNS 设置**”。

1.  在“**A/AAAA 记录(IP 地址)**”部分的“**IP 地址(A 记录)**”区域中，选择“**CNAME**”。

1. 在“**别名:**”框中，只键入或复制并粘贴下表中的“**别名**”值。

    |创建子域|别名|
    |:----|:----|
    |自动发现|autodiscover.outlook.com|

1. 选中“**我知道**”声明的复选框。

1. 选择“**保存**”。

### <a name="additional-cname-records"></a>其他 CNAME 记录

以下过程中的其他 CNAME 记录启用了 Skype for Business Online 服务。 使用已创建的两条 CNAME 记录所用的相同步骤。

**创建第三个子域 (Lyncdiscover)**

1.  在“**子域概述**”部分中，选择“**创建子域**”。

1.  在新子域的“**创建子域**”框中，只键入或复制并粘贴下表中的“**创建​​子域**”值。（将在后一步中添加“**别名**”值。）

    |创建子域|别名|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  选择 **创建子域**。

1.  在“域中心”页面上，选择“**管理子域**”。

1.  在 **子域概述** 部分中，找到刚刚创建的 lyncdiscover 子域，然后选择该子域的面板 (v) 控件。在 **子域设置** 区域中，选择“**编辑 DNS 设置**”。

1.  在“**A/AAAA 记录(IP 地址)**”部分的“**IP 地址(A 记录)**”区域中，选择“**CNAME**”。

1.  在“**别名:**”框中，只键入或复制并粘贴下表中的“**别名**”值。

    |创建子域|别名|
    |:----|:----|
    |lyncdiscover|webdir.online.lync.com|

1.  选中“**我知道**”声明的复选框，然后选择“**保存**”。

1.  在“**编辑 DNS 设置**”对话框中，选择“**是**”。

**创建第四个子域 (SIP)**

1.  在“**子域概述**”部分中，选择“**创建子域**”。

1.  在新子域的“**创建子域**”框中，只键入或复制并粘贴下表中的“**创建​​子域**”值。（将在后面一个步骤中添加“**别名**”值。）

    |创建子域|别名|
    |:----|:----|
    |sip|sipdir.online.lync.com|  

1.  选择 **创建子域**。

1.  在“域中心”页面上，选择“**管理子域**”。

1.  在“**子域概述**”部分中，找到刚才创建的 sip 子域，然后选择该子域的面板 (v) 控件。 <br/> 在“**子域设置**”区域中，选择“**编辑 DNS 设置**”。

1.  在“**A/AAAA 记录(IP 地址)**”部分的“**IP 地址(A 记录)**”区域中，选择“**CNAME**”。

1.  在“**别名:**”框中，只键入或复制并粘贴下表中的“**别名**”值。

    |创建子域|别名|
    |:----|:----|
    |sip|sipdir.online.lync.com|

1.  选中“**我知道**”声明的复选框，然后选择“**保存**”。

1.  在“**编辑 DNS 设置**”对话框中，选择“**是**”。

### <a name="cname-records-needed-for-mdm"></a>MDM 所需的 CNAME 记录

按照用于其他四条 CNAME 记录的过程进行操作，但需提供以下值：

|创建子域|别名|
|:----|:----|
|enterpriseregistration|enterpriseregistration.windows.net|
|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com|
