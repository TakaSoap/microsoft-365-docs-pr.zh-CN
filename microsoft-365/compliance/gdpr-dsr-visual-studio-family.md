---
title: 针对 GDPR 的 Visual Studio 系列数据主体请求
description: 针对 GDPR 的 Visual Studio 系列数据主体请求
keywords: Visual Studio, Visual Studio Code, Visual Studio for Mac, Visual Studio 文档, 隐私, GDPR
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: PoulChapman
ms.author: olholder
manager: pchapman
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 5b07cefa4a850d5de7c858f180c8f7688fd0a6d7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286920"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr"></a>针对 GDPR 的 Visual Studio 系列数据主体请求

根据欧盟[一般数据保护条例 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm)，用户（在条例中称为_数据主体_）有权管理其个人数据。根据 GDPR，个人数据的定义非常广泛，包括与身份已识别或可识别的自然人相关的任何数据。根据 GDPR，数据主体有权对自己的个人数据执行以下操作：获取个人数据副本、请求更正个人数据、限制个人数据处理、删除个人数据或接受电子格式的个人数据。数据主体为了对自己的个人数据执行操作而向数据控制者（雇主或有权控制个人数据的其他类型的机构或组织）发出的正式请求称为_数据主体请求_或 DSR。有关 GDPR 的 一般信息，请参阅[服务信任门户的 GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) 部分。

## <a name="products-covered-by-this-guide"></a>本指南涵盖的产品

本指南介绍如何使用 Microsoft 工具来导出或删除经过身份验证的（已登录）会话在使用 Visual Studio 和 Visual Studio for Mac 以及针对它们和 Visual Studio Code 的 Microsoft 扩展过程中所收集的个人数据。本指南还介绍如何对使用 Visual Studio 开发人员社区、NuGet.org 和 ASP.NET 网站时所收集的个人数据提出数据主体请求。这些产品可能允许使用非 Microsoft 工具和扩展，Microsoft 不是这些工具和扩展的数据处理者或控制者。用户应联系工具或扩展提供商，以了解针对这些工具和扩展的个人数据和收集策略。

## <a name="additional-privacy-information"></a>其他隐私信息

产品附带的 Microsoft 软件许可条款，[Microsoft 隐私声明](https://go.microsoft.com/fwlink/?LinkId=660726)和 [Microsoft 有关 GDPR 的义务](https://docs.microsoft.com/legal/gdpr)介绍了我们的数据处理做法。

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a>Visual Studio, Visual Studio for Mac 和 Visual Studio Code

### <a name="personal-data-we-collect"></a>我们收集的个人数据

根据 GDPR，Microsoft 作为数据处理者 从用户那里收集我们所需的数据，在提供对 Visual Studio 和 Visual Studio for Mac，以及对它们和 Visual Studio Code 的 Microsoft 扩展的使用体验的同时，提升使用体验。数据分为两类：客户数据和系统生成的日志。客户数据包括这些产品执行其提供的服务时所需的用户可识别事务和交互数据。例如，为了向用户提供漫游设置等个性化体验，我们需要收集用户帐户信息和设置数据。系统生成的日志是用于帮助标识和排查问题并改进我们的产品和服务的使用情况数据或诊断数据，可能也包含有关最终用户的可识别信息（例如，用户名）。系统生成的日志的保留期不超过 18 个月。例如，针对产品每天的使用情况聚合系统生成的日志，并包含使用日期、使用的产品（例如，“Visual Studio 2017”）、执行的操作（例如，“vs/core/packagecostsummary/solutionload”）以及执行操作的次数，如此示例中所示：

```
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

有关详细信息，请参阅[由 Visual Studio 收集的系统生成的日志](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection)。

DSR 只能对附加到经过身份验证的标识的个人数据提供服务。例如，由于 Visual Studio Code 不支持登录，因此，来自 Visual Studio Code 的系统生成的日志无法被附加到经过身份验证的标识，所以无法对其提供服务。但是，针对 Visual Studio Code 的某些 Microsoft 扩展可提供经过身份验证的数据，DSR 可对此数据提供服务。有关详细信息，请参阅 [GPDR 和 Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code)。一般情况下，我们不存储 Visual Studio 2013 和更早版本的数据；但是，某些扩展和组件可能提供附加到经过身份验证的标识的数据，DSR 可对其提供服务，如下所述。

### <a name="how-users-can-control-personal-data"></a>用户如何控制个人数据

Visual Studio 2015 及更高版本、Visual Studio for Mac 和 Visual Studio Code 为用户提供了以下方法来停止数据收集，并为作为控制者的你提供了导出或删除已被收集的数据的方法。

#### <a name="in-app-settings"></a>应用内设置

用户可以控制这些产品的隐私设置。有关详细信息，请参阅以下内容

- [如何在 Visual Studio 中管理隐私设置](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program)。
- [如何在 Visual Studio for Mac 中管理隐私设置](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program)。
- [如何在 Visual Studio Code 中禁用遥测报告](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting)。

#### <a name="exporting-or-deleting-data"></a>导出或删除数据

控制者可以使用两种方法中的任意一种来管理客户数据以及从其数据主体收集的系统生成的日志，具体取决于其 Visual Studio 系列产品或 Microsoft 扩展注册的方式。在某些情况下，必须同时使用这两种方法。两者都允许控制者下载由该方法管理的活动历史记录的副本。关闭 AAD 或 MSA 帐户将删除相关联的 Visual Studio 客户数据，并对系统生成的日志中与这些产品相关的个人可识别数据匿名处理。匿名处理的系统生成的日志的保留期限不超过 18 个月。

- 使用由 Azure 租户支持的帐户（例如，AAD 帐户或与 Azure 订阅关联的 MSA 帐户）注册 Visual Studio 系列产品的用户可以按照[针对 GDPR 的 Azure 数据主体请求](gdpr-dsr-azure.md)中的说明执行操作。
- 未使用由 Azure 租户支持的帐户（例如，使用 Microsoft 帐户 (MSA) 的许多帐户）注册 Visual Studio 系列产品的用户可以使用其 Microsoft 帐户提供的[基于 Web 的 Microsoft 隐私响应中心](https://aka.ms/userprivacysite)跨多个 Microsoft 服务来查看、控制和删除绑定到他们的 Microsoft 帐户的活动数据。在此应用场景中，用户是自己个人数据的控制者。

> [!NOTE]
> 当 MSA 帐户持有者删除其帐户时，所有与这些产品相关的个人可识别数据都将被删除（无论该帐户是否受 Azure 租户支持），并且将对系统生成的日志匿名处理。

对于 Visual Studio 2013，我们收集的数据将经过匿名处理。对于 Visual Studio 2012 和之前的版本，我们将在收到请求后立即删除数据。在这两种情况下，在以后都没有查看、导出或删除的内容。

## <a name="visual-studio-developer-community"></a>Visual Studio 开发人员社区

我们支持通过[开发人员社区](https://developercommunity.visualstudio.com)网站提交的[一般数据保护条例 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 请求。用户可以查看、导出或删除自己的反馈数据。

### <a name="personal-data-we-collect"></a>我们收集的个人数据

Microsoft 收集数据，帮助我们重现和排查你报告的 Visual Studio 系列产品中的问题。此数据包括个人数据和公共反馈。个人数据包括：

- 你的[开发人员社区](https://developercommunity.visualstudio.com)个人资料信息；
- 首选项和通知；
- 通过[报告 Visual Studio 中的问题](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)或通过[开发人员社区](https://developercommunity.visualstudio.com)提供的附件和系统生成的日志；
- 你的投票。

公共反馈包括：报告的问题、评论和解决方案。

### <a name="how-users-can-control-personal-data"></a>用户如何控制个人数据

#### <a name="view"></a>查看

若要查看与你的反馈相关的数据，请执行以下步骤：

1. 登录到[开发人员社区](https://developercommunity.visualstudio.com)。 在右上角，单击个人资料并选择“个人资料和首选项”****。
2. 单击任何“个人资料”****、“通知”****、“活动”**** 和“附件”**** 选项卡，查看提交到反馈系统的数据。
   1. “个人资料”**** 指的是你的[开发人员社区](https://developercommunity.visualstudio.com)个人资料，包括用户名、电子邮件地址、个人相关信息等。
   2. “通知”**** 是你控制接收电子邮件通知的方式。
   3. “活动”**** 将为你提供你曾活跃的反馈项（发表的帖子、评论等）和执行的活动。
   4. “附件”**** 是你的附件历史记录的列表，格式如下：`FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`

#### <a name="export"></a>导出

可以将反馈数据作为 DSR 的一部分导出，我们将创建一个或多个 .zip 存档，它将包括：

- 你的[开发人员社区](https://developercommunity.visualstudio.com)个人资料信息；
- 首选项和通知设置；
- 通过[报告 Visual Studio 中的问题](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)或通过[开发人员社区](https://developercommunity.visualstudio.com)提供的附件。

> [!NOTE]
> 我们将从你的存档中排除你提供的以下公共反馈：评论、解决方案、报告的问题。

若要开始导出，请执行以下步骤：

1. 登录到[开发人员社区](https://developercommunity.visualstudio.com)。 在右上角，单击个人资料并选择“个人资料和首选项”****。
2. 单击“隐私”**** 选项卡，然后单击“创建存档”****，请求导出数据。
3. “存档状态”**** 将更新，显示我们正在准备数据。准备数据的时间取决于我们需要导出的数据量。
4. 数据准备就绪后，我们会向你发送一封电子邮件。
5. 单击电子邮件中的“下载存档”****，或返回到“隐私”选项卡以下载数据。

> [!NOTE]
> - 如果你在“通知”选项卡中选择了不接收通知，我们将不会发送电子邮件。
> - 如果请求重新导出，我们将删除旧存档，并创建新存档。

#### <a name="delete"></a>删除

删除操作将从[开发人员社区](https://developercommunity.visualstudio.com)中删除与你相关的以下信息：

- 个人资料信息；
- 首选项和通知设置；
- 通过[报告 Visual Studio 中的问题](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)或通过[开发人员社区](https://developercommunity.visualstudio.com)提供的附件。
- 你的投票

> [!NOTE]
> 我们不会删除以下公共信息，但会对其进行匿名处理：你的评论、你的解决方案以及你报告的问题。
>
> [!IMPORTANT]
> 删除 AAD 或 MSA 帐户将会触发[开发人员社区](https://developercommunity.visualstudio.com)的删除过程。

若要启动删除操作，请执行以下步骤：

1. 登录到[开发人员社区](https://developercommunity.visualstudio.com)。在右上角，单击个人资料并选择“个人资料和首选项”****。
2. 单击“隐私”**** 选项卡，然后单击“删除数据和帐户”**** 开始删除你的数据。
3. 将显示确认屏幕。
4. 在框中键入“delete”，然后单击“删除我的帐户”****。

单击“删除我的帐户:”**** 后，

- 你的帐户将注销。
- 我们将删除你的[开发人员社区](https://developercommunity.visualstudio.com)帐户、你的个人数据以及附件。
- 我们将对你的公共反馈进行匿名处理。你的公共反馈仍会在开发人员社区显示，但会指示此反馈是由匿名用户报告的。
- 在删除你的帐户后，我们不会向你发送电子邮件，因为你已不再存在于系统中。
- 如果报告新问题或登录到[开发人员社区](https://developercommunity.visualstudio.com)，你将被标识为新用户。
- 如果你将自己的帐户从[开发人员社区](https://developercommunity.visualstudio.com)中删除，我们将不会从其他 Microsoft 服务中删除该帐户。

## <a name="xamarin-forums-and-bugzilla"></a>Xamarin 论坛和 Bugzilla

### <a name="personal-data-we-collect"></a>我们收集的个人数据

Microsoft 通过 [Xamarin 论坛](https://forums.xamarin.com)用户社区和 [Xamarin Bugzilla](https://bugzilla.xamarin.com/) bug 报告网站收集你提供的数据，帮助我们重现和排查你在使用 Microsoft 产品和服务时可能遇到的问题。此数据包括个人数据和公共反馈。我们收集的个人数据是用户帐户数据（例如，与你的 Xamarin 论坛或 Bugzilla 帐户相关联的用户名和电子邮件地址），我们收集的公共反馈包括你通过 Xamarin 论坛或 Xamarin Bugzilla bug 报告网站所提供的 bug、问题、评论和解决方案。

### <a name="how-you-can-control-your-data"></a>如何控制数据

#### <a name="xamarin-forums"></a>Xamarin 论坛

##### <a name="view"></a>查看

具有 Xamarin 论坛活动帐户的用户可以从其 Xamarin 论坛帐户页查看个人数据和公共反馈（例如，发布的所有主题和帖子）。用户还可以通过帐户页面来编辑个人数据。

##### <a name="export"></a>导出

Xamarin 论坛由第三方 Vanilla 论坛托管。若要请求导出你的公共数据，应联系 forums@xamarin.com（由 Xamarin 团队监控）。我们将直接与 Vanilla 论坛协同处理此请求。

##### <a name="delete"></a>Delete

Xamarin 论坛由第三方 Vanilla 论坛托管。若要请求删除你的个人数据和公共数据，请联系 forums@xamarin.com（由 Xamarin 团队监控）。然后，我们将根据用户请求手动删除个人数据。

#### <a name="bugzilla-for-xamarin"></a>Xamarin 的 Bugzilla

##### <a name="view"></a>查看

具有 Xamarin Bugzilla 活动帐户的用户可以查看他们已报告的所有 bug，以及他们向 bug 添加的所有注释，方法是单击 Xamarin Bugzilla 主页上相应的链接。

##### <a name="export"></a>导出

不支持导出个人数据。

##### <a name="delete"></a>删除

若要请求删除 Xamarin 的 Bugzilla bug 报告网站中所使用的个人数据，用户可以关闭其 Xamarin Bugzilla 帐户，方法是导航到[用户首选项页](https://bugzilla.xamarin.com/userprefs.cgi)并选择“关闭帐户”**** 选项卡。输入 Bugzilla 密码并勾选“确认你已了解此操作将永久删除你的帐户”框。收到删除请求后，将不会删除用户已发布到 Xamarin Bugzilla 的公共反馈（例如，bug、问题、评论和解决方案）。公共反馈改为以匿名形式显示，这是通过删除与提交删除请求的用户所创建的任何公共反馈关联的名称和电子邮件地址实现的。

## <a name="nuget"></a>NuGet

有关针对 NuGet.org 的 DSR 的详细信息，请参阅 [NuGet 用户数据请求](https://docs.microsoft.com/nuget/policies/data-requests)。

## <a name="aspnet"></a>ASP.NET

有关针对 ASP.NET 网站的 DSR 的信息，请参阅 [ASP.NET 网站和 GDPR 数据主体请求处理](https://www.asp.net/gdpr)。

## <a name="iisnet"></a>IIS.NET

有关针对 IIS.NET 网站的 DSR 的信息，请参阅 [IIS.NET 网站和 GDPR 数据主体请求处理](https://www.iis.net/gdpr)。

## <a name="other-visual-studio-family-services"></a>其他 Visual Studio 系列服务

### <a name="surveymonkey"></a>SurveyMonkey

有时，我们会邀请客户通过 SurveyMonkey 提供有关这些产品的反馈。此数据将在 28 天内删除。为这些产品提供数据主体请求服务时，如果我们已验证了调查响应，会将其添加到导出和删除数据主体请求中。

### <a name="uservoice"></a>UserVoice

我们邀请客户在 UserVoice.com 网站上提供有关这些产品的产品建议。这些网站是由 UserVoice 独立运营的，数据主体请求由 UserVoice 管理。

- [https://visualstudio.uservoice.com/](https://visualstudio.uservoice.com/)
- [https://aspnet.uservoice.com/](https://aspnet.uservoice.com/)
- [https://xamarin.uservoice.com/](https://xamarin.uservoice.com/)

有关此数据的数据主体请求，请参阅[如何导出数据](https://feedback.uservoice.com/knowledgebase/articles/1850245-export-my-personal-data)或[如何删除数据](https://feedback.uservoice.com/knowledgebase/articles/1848856-delete-my-profile-information)上的 UserVoice 指南。

## <a name="learn-more"></a>了解更多

- [Microsoft 对我们公开发布的企业软件产品的客户的 GDPR 义务](https://docs.microsoft.com/legal/gdpr)
- [Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [服务信任门户](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Microsoft 隐私仪表板](https://account.microsoft.com/privacy)
- [Microsoft 隐私响应中心](https://aka.ms/userprivacysite)
- [针对 GDPR 的 Azure 数据主体请求](gdpr-dsr-azure.md)
