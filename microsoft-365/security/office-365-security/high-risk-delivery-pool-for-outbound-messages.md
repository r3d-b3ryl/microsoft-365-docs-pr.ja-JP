---
title: 送信方向の配信のプール
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 配信プールを使用して、Microsoft 365 データセンター内の電子メール サーバーの評判を保護する方法について説明します。
ms.openlocfilehash: 83ea21a9230240f1339513efc75587f3d84733cb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827739"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="b8ae0-103">送信方向の配信のプール</span><span class="sxs-lookup"><span data-stu-id="b8ae0-103">Outbound delivery pools</span></span>

<span data-ttu-id="b8ae0-104">Microsoft 365 データセンターのメール サーバーでは、スパムを送信したメールが一時的に有効な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="b8ae0-105">たとえば、オンプレミスのメール組織のマルウェアまたは悪意のあるスパム攻撃で、Microsoft 365 経由で送信メールを送信したり、Microsoft 365 アカウントに問題が侵害されたりした場合などです。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="b8ae0-106">攻撃者は、Microsoft 365 転送経由でメッセージを中継して検出の回避も試みてください。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-106">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="b8ae0-107">これらのシナリオによって、影響を受ける Microsoft 365 データセンター サーバーの IP アドレスがサード パーティのブロック リストに表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-107">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="b8ae0-108">このブロック リストを使用している送信先メール組織は、これらのメッセージ ソースからのメールを拒否します。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-108">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="b8ae0-109">危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="b8ae0-109">High-risk delivery pool</span></span>
<span data-ttu-id="b8ae0-110">これを防ぐため、スパムとして判断された、またはサービスや送信スパム ポリシーの送信制限を超えるすべての送信メッセージが、危険度の高[the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)い配信プール[outbound spam policies](configure-the-outbound-spam-policy.md)_で送信されます_。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-110">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="b8ae0-111">危険度の高い配信プールとは、送信電子メール用の独立した IP アドレス プールです。送信電子メール専用のルーティング プールです (スパムやバックス [キャターなど](backscatter-messages-and-eop.md))。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-111">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="b8ae0-112">高リスク配信プールを使用すると、送信電子メールに対して通常の IP アドレス プールがスパムを送信するのを防止できます。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-112">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="b8ae0-113">送信電子メールの通常の IP アドレス プールは、"高品質" メッセージの送信を維持します。これは、これらの IP アドレスが IP 禁止一覧に表示される可能性を低減します。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-113">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="b8ae0-114">非常に、より危険度の高い配信プールの IP アドレスは IP 禁止一覧に残されますが、これは設計上のためです。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-114">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="b8ae0-115">多くの電子メール組織が危険性の高い配信プールからメッセージを受け付けないため、意図された受信者への配信は一切切必要しません。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-115">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="b8ae0-116">詳細については、「送信スパムの [制御」を参照してください](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-116">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b8ae0-117">送信元メール ドメインに A レコードがなく、パブリック DNS で MX レコードが定義されていないメッセージは、スパムや送信制限の処分に関係なく、常に危険度の高い配信プールでルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-117">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="b8ae0-118">バウンス メッセージ</span><span class="sxs-lookup"><span data-stu-id="b8ae0-118">Bounce messages</span></span>

<span data-ttu-id="b8ae0-119">送信用の危険度の高い配信プールは、すべての配信不能レポート (NDR、バウンス メッセージ、配信状態通知、DSN とも呼ばれる) の配信を管理します。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-119">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="b8ae0-120">NDR のスージングの原因としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-120">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="b8ae0-121">サービスを使用している顧客のいずれかに影響を与えるスプーフィング キャンペーン。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-121">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="b8ae0-122">ディレクトリ取得攻撃。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-122">A directory harvest attack.</span></span>
- <span data-ttu-id="b8ae0-123">スパム攻撃。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-123">A spam attack.</span></span>
- <span data-ttu-id="b8ae0-124">問題の電子メール サーバー。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-124">A rogue email server.</span></span>

<span data-ttu-id="b8ae0-125">これらのすべての問題により、サービスが処理する NDR の数が多く増えてしう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-125">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="b8ae0-126">多くの場合、このような NDR は、他の電子メール サーバーやサービス (バックスキャター _[とも呼ばれる) へのスパムのように見えることもあります](backscatter-messages-and-eop.md)_。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-126">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="b8ae0-127">リレー プール</span><span class="sxs-lookup"><span data-stu-id="b8ae0-127">Relay pool</span></span>

<span data-ttu-id="b8ae0-128">Microsoft 365 から転送または中継されるメッセージは、特別な中継プールを使用して送信されます。最終的な送信先は実際の送信者として Microsoft 365 とは見なされないからです。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-128">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="b8ae0-129">また、Microsoft 365 からメールの自動転送または中継に対しては正当で無効なシナリオがあるため、このトラフィックを分離するのも重要です。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-129">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="b8ae0-130">危険度の高い配信プールと同様に、別の IP アドレス プールが中継されたメールに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-130">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="b8ae0-131">このアドレス プールは頻繁に変更される可能性があから、公開されません。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-131">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="b8ae0-132">Microsoft 365 は、元の送信者が正当なものであるかどうかを検証して、転送されたメッセージを不確認できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-132">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="b8ae0-133">これを行うためには、メール認証 (SPF、DKIM、および DMARC) がメッセージが Microsoft に送信されるときに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-133">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="b8ae0-134">送信者が認証できる場合は、送信者書き換えを使用して、転送されたメッセージが信頼できる送信元からのものであることが受信者にわかるようにします。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-134">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="b8ae0-135">この操作のしくみと、送信ドメインが [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)で認証に合格したことを確認するために役立つ方法を参照できます。</span><span class="sxs-lookup"><span data-stu-id="b8ae0-135">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
