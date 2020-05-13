---
title: 送信メッセージにおける危険度の高い配信プール
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 高リスク配信プールを使用して、Microsoft 365 データセンター内の電子メールサーバーの評価を保護する方法について説明します。
ms.openlocfilehash: 190dc3bd7ed2a6cddb23c8bc7c117dee30fd4f13
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209189"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="5d650-103">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="5d650-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="5d650-104">Microsoft 365 データセンター内の電子メールサーバーは、一時的にスパムを送信している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d650-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="5d650-105">たとえば、Microsoft 365 を介して送信メールを送信する社内電子メール組織、または Microsoft 365 アカウントを侵害したマルウェアまたは悪意のあるスパム攻撃。</span><span class="sxs-lookup"><span data-stu-id="5d650-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="5d650-106">これらのシナリオでは、影響を受ける Microsoft 365 datacenter サーバーの IP アドレスが、サードパーティのブロックリストに表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5d650-106">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="5d650-107">[宛先電子メール] これらのブロックリストを使用する組織は、それらのメッセージソースからの電子メールを拒否します。</span><span class="sxs-lookup"><span data-stu-id="5d650-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="5d650-108">これを防ぐために、スパムであると判断された、または、[サービス](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)または[送信スパムポリシー](configure-the-outbound-spam-policy.md)の送信制限を超えている Microsoft 365 datacenter サーバーからのすべての送信メッセージは、_高リスク配信プール_を経由して送信されます。</span><span class="sxs-lookup"><span data-stu-id="5d650-108">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="5d650-109">高リスク配信プールは、"低品質" メッセージの送信にのみ使用される送信電子メールのセカンダリ IP アドレスプールです (たとえば、スパムや[バックスキャター](backscatter-messages-and-eop.md))。</span><span class="sxs-lookup"><span data-stu-id="5d650-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="5d650-110">高リスク配信プールを使用すると、送信電子メールの通常の IP アドレスプールがスパムを送信するのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="5d650-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="5d650-111">送信電子メール用の通常の IP アドレスプールは、"高品質" メッセージを送信するという評価を維持します。これにより、IP アドレスが IP 禁止一覧に表示される可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="5d650-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="5d650-112">高リスク配信プールの IP アドレスが IP 禁止一覧に配置される本当の可能性は残っていますが、これは仕様です。</span><span class="sxs-lookup"><span data-stu-id="5d650-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="5d650-113">多くの電子メール組織は高リスク配信プールからのメッセージを受け付けないため、目的の受信者への配信は保証されません。</span><span class="sxs-lookup"><span data-stu-id="5d650-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="5d650-114">詳細については、「[送信スパムの制御](outbound-spam-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d650-114">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5d650-115">送信元の電子メールドメインにレコードがなく、パブリック DNS で定義されている MX レコードが、スパムや送信制限の廃棄に関係なく、常に高リスク配信プールを経由してルーティングされるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5d650-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="5d650-116">メッセージをバウンスする</span><span class="sxs-lookup"><span data-stu-id="5d650-116">Bounce messages</span></span>

<span data-ttu-id="5d650-117">送信高リスク配信プールは、配信不能レポート (Ndr、バウンスメッセージ、配信状態通知、または Dsn とも呼ばれます) の配信を管理します。</span><span class="sxs-lookup"><span data-stu-id="5d650-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="5d650-118">Ndr のサージには、次のような原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="5d650-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="5d650-119">サービスを使用しているお客様の1人に影響を与えるスプーフィングキャンペーン。</span><span class="sxs-lookup"><span data-stu-id="5d650-119">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="5d650-120">ディレクトリハーベスト攻撃。</span><span class="sxs-lookup"><span data-stu-id="5d650-120">A directory harvest attack.</span></span>
- <span data-ttu-id="5d650-121">スパム攻撃。</span><span class="sxs-lookup"><span data-stu-id="5d650-121">A spam attack.</span></span>
- <span data-ttu-id="5d650-122">不正な電子メールサーバー。</span><span class="sxs-lookup"><span data-stu-id="5d650-122">A rogue email server.</span></span>

<span data-ttu-id="5d650-123">これらのすべての問題により、サービスによって処理されている Ndr の数が急激に増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d650-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="5d650-124">多くの場合、これらの ndr は他の電子メールサーバーおよびサービス (_[バックスキャター](backscatter-messages-and-eop.md)_ とも呼ばれます) に対してスパムに見えます。</span><span class="sxs-lookup"><span data-stu-id="5d650-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
