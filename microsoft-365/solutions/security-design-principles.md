---
title: 您可以 sail 的安全障碍—一个架构师的视点
description: 说明。
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: cdb6b557bf2f46a2338d929547167cf89a048695
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522272"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>您可以 sail 的安全障碍—一个架构师的视点

在本文中， [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/)，Cybersecurity 架构师（Microsoft）介绍了她在企业组织中遇到的最大安全难题，并建议了在这些障碍方面 sailing 的方法。 

## <a name="about-the-author"></a>作者简介

![Kozeta Garrett 照片](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

在我的角色中，作为云安全性架构师，我已与多个组织合作，以提供有关为迁移到 Microsoft 365 和 Azure 的客户设计和实施安全体系结构的战略性和技术指导，开发企业安全解决方案，并帮助转换安全体系结构和区域性以实现商业弹性。 我的体验包括事件检测和响应、恶意软件分析、渗透测试，并建议对 IT 安全和防御状态进行改进。 我非常关心的主要转变导致安全作为业务启用码，包括现代化工作。

大多数情况下，了解在最近几年中采用安全现代化思维方式的组织在很大程度上，让他们能够以安全的方式继续远程操作，而不考虑最近的 COVID-19 的情况。 遗憾的是，这些情况也为一些客户提供了唤醒呼叫，这些客户尚未准备好满足此即时需求。 许多组织都认识到，他们必须快速现代化、淘汰其累积的 IT 安全债务，并提高安全状态整夜，以便它们可以在这些极不寻常的情况下运行。

好消息是 Microsoft 已 curated 一些有用的资源，帮助组织快速提高其安全状态。 除了这些资源之外，我想要分享我在客户每天遇到的最大挑战，因为您可以 sail 这些障碍。

我目前居住在北弗吉尼亚州，靠近我们所在国家/地区的首都特区 DC。 我只喜欢每种形式的户外活动和练习，如运行、biking、hiking 和 swimming。 若要对付这些，我将喜欢的烹饪、gourmet 食物和旅行量。 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>从云采用开始时向安全团队提供合作伙伴

首先，我无法强调组织中的团队在开始时的重要性。 在云采用和设计的早期阶段，安全团队必须成为关键合作伙伴。 这意味着，仅让安全团队支持云采用，而不仅是针对企业的新增功能（如安全移动设备、完整功能应用程序的强大用户体验），还可以利用存储、AI 和计算分析功能，帮助解决新的和旧的安全难题。 安全团队必须包含在管理此班次的所有方面，包括人员（文化）、流程（培训）和成功的技术。 这也意味着投资在安全操作中心（SOC）方面的现代化和持续改进。 配合使用，将安全策略与业务策略和环境趋势相协调，以确保数字转换安全地进行。 完成此操作后，组织将开发能够更快地适应更改的能力，包括对业务、IT 和安全性的更改。 

在这些操作和 SOC 团队之间没有真正的合作关系的情况下，我看到客户在不到障碍的情况下会发生最多的情况。 尽管正在对运营团队进行 pressured 和规定采用云的最终期限，但安全团队并不总是包括在修改和规划全面安全策略的过程的早期阶段。 这涉及集成不同的云组件以及本地中的组件。 这缺乏合作关系进一步 trickles 到不同的团队，这些团队似乎在思洛存储器中使用，以实现其特定组件的控制，从而增加了实现、故障排除和集成的复杂性。

Sail 通过这些障碍的客户在运营和治理以及安全与风险管理团队之间建立了充分的合作关系，以 revamp 保护混合云工作负载的安全策略和要求。 他们将重点放在最终安全目标和成果上—数据保护和系统和服务的可用性与 cybersecurity 治理、风险和合规性要求一致。 这些组织在其运营与治理团队和 SOC 之间开发早期阶段的合作伙伴关系，这对安全设计方法至关重要，并将其投资的价值最大化。 

## <a name="build-a-modern-identity-based-security-perimeter"></a>构建新式（基于身份的）安全外围环境

接下来，采用零信任体系结构方法。 这将从构建新式的基于标识的安全外围环境开始。 设计安全体系结构，其中每个访问尝试（无论是本地还是云）在验证后都被视为不可信— "从不信任，总是验证"。 此设计方法不仅提高安全性和生产效率，还允许用户从任何设备类型的任何地方工作。 Microsoft 365 附带的完善的云控件可帮助您保护用户的身份，同时根据用户风险级别控制对宝贵资源的访问。

有关建议的配置，请参阅[Identity and device access 配置](../enterprise/microsoft-365-policies-configurations.md)。 

## <a name="transition-security-controls-to-the-cloud"></a>将安全控制转换为云

许多安全团队仍在使用针对所有内部部署环境构建的传统安全最佳做法，包括维护 "网络外围安全" 并尝试 "强制" 本地安全工具和控件到云解决方案。 此类控件不是为云设计的，不能实现，也不会妨碍采用新式云功能。 在网络外围安全方法工作的过程和工具已证明效率低、obstructive 到云功能，并且不允许利用新式和自动安全功能。

您可以通过将防护策略转移到云管理的保护、自动调查和修正、自动化的笔测试、高级威胁防护和事件分析，来 sail 此障碍。 使用新式设备管理解决方案的客户已实现跨所有设备（无论智能手机、个人计算机、便携式计算机或平板电脑）的自动化管理、标准化修补、防病毒、策略实施和应用程序保护。 这样就无需使用 VPN、Microsoft System Center Configuration Manager （SCCM）和 Active Directory 组策略。 这与条件访问策略结合使用，可提供强大的控制和可见性，并可简化对资源的访问，无论用户在哪里运行。

## <a name="strive-for-best-together-security-tools"></a>努力实现最佳安全工具

另一个障碍我看到客户 stumble 的是，采用了最佳的安全工具方法。 不断对 "最佳" 点解决方案进行分层，以解决新出现的安全需求，从而导致企业安全细分。 即使获得最佳意图，大多数环境中的工具也不会集成，因为这会导致成本太高且复杂。 这反过来会在可见性方面产生空隙，因为要会审的通知数多于团队可以处理的通知数。 在新工具上重新培训 SecOps 团队也会成为一项不断的挑战。

"简单来说更好" 的做法也适用于安全性。 在默认情况下，通过采用 "最佳组合" 策略来 sail 此障碍，而不是在 "最佳" 工具的后面，通过将 "最佳结合" 策略结合使用。 Microsoft 安全功能使用跨应用程序、用户和云的集成威胁保护来保护您的整个组织。 集成使组织能够通过在进入和快速补救攻击中包含攻击者来提高灵活性并降低风险。

## <a name="balance-security-with-functionality"></a>将安全性与功能进行权衡

由于我的 cybersecurity 背景和体验较长，因此我倾向于从现成的最安全配置开始，并允许组织根据其运营和安全需求放宽安全配置。 但是，这可能会带来 hefty 的损失，并导致用户体验不佳。 随着许多组织的了解，如果用户的安全性过于困难，他们将找到解决您的方法，包括使用非托管云服务。 就像我接受的那样，我已意识到必须实现精密的功能-安全平衡。

实现用户完成工作所需的组织将完成其工作所需的工作，以确认 "影子 IT 工作" 不需要进行反击。 他们认识到 IT 员工在对其进行分段和未批准的 SaaS 应用程序的工作时，有最大的违犯者。 他们已将其战略转移到鼓励使用（而不是抑制），并将重点放在缓解其可能造成的风险风险方面。 这些组织的安全团队不要求通过反向代理或 VPN 来阻止、记录和发送所有内容。 相反，这些安全团队会加倍努力保护宝贵而敏感的数据，使其不会暴露给错误的方或恶意应用程序。 它们可以保护数据的完整性。 他们充分利用了更高级的云信息保护功能，包括加密、安全多重身份验证、自动化风险和合规性以及云应用安全代理（CASB）功能，同时允许甚至在多个平台上鼓励受保护的共享。 他们正在将其隐藏在 inspiring 创造性、生产力和协作中，使其业务能够在竞争优势中保持。


## <a name="adopt-a-methodical-approach"></a>采用一种系统方式 

在不同组织中实施云安全性时遇到的大多数难题（无论是哪种行业），都非常相似。 首先，虽然有大量有关特定功能和功能的有用文档，但在组织级别有一些会对其应用的内容有一定程度的混淆，安全功能重叠以及应如何集成功能。 此外，对于哪些安全功能已预先配置为现成且需要由组织进行配置的情况也有一层不确定性。 此外，SOC 团队还没有充分的风险、培训或预算分配来准备快速云采用和对其组织进行数字转换的准备工作。

为了帮助您清除这些障碍，Microsoft 已 curated 多个资源，旨在帮助您对安全策略和实现采取一种系统方式。 


|Resource   |详细信息  |
|---------|---------|
|[安全团队为支持在家办公需完成的首要任务](../security/top-security-tasks-for-remote-work.md)      | 如果你发现自己突然支持大多数家庭工作劳动力，本文将帮助你快速提升安全性。 其中包括基于你的许可计划的最佳推荐任务。    |
|[Microsoft 365 商业决策人的安全性](../security/Microsoft-365-security-for-bdm.md)    | 如果你有时间进行更全面的计划，本文将包含跨越 Microsoft 365 的建议，这些建议按受攻击面设定优先级。 它甚至附带有一个电子表格，可用于对许可和区域进行排序（如标识、威胁防护和监控）。  |
|[Microsoft 安全体系结构建议](https://docs.microsoft.com/security/compass/compass)    | 如果您是安全架构师，请务必查看按学科组织的安全建议，包括标识、网络和安全操作。   |
|[Microsoft 安全操作建议](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|了解有关设置和运行安全操作中心（SOC）的 Microsoft 建议 |
|[首席信息安全监察官（CISO）研讨会培训](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | 如果你不熟悉云安全性，请不要错过此系列视频。        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | 通过 Microsoft 实现安全策略和体系结构的技术指导。        |
| | |

所有这些资源都旨在用作起点，并可适应组织的需要。 

