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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 配信プールを使用して、Microsoft 365 データセンター内の電子メール サーバーの評判を保護する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289807"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="ad731-103">送信方向の配信のプール</span><span class="sxs-lookup"><span data-stu-id="ad731-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ad731-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ad731-104">**Applies to**</span></span>
- [<span data-ttu-id="ad731-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ad731-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ad731-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ad731-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ad731-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad731-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ad731-108">Microsoft 365 データセンターの電子メール サーバーは、一時的にスパムを送信した場合に有悪な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="ad731-109">たとえば、Microsoft 365 経由で送信メールを送信するオンプレミスの電子メール組織でのマルウェアや悪意のあるスパム攻撃や、侵害された Microsoft 365 アカウントなどです。</span><span class="sxs-lookup"><span data-stu-id="ad731-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="ad731-110">攻撃者は、Microsoft 365 の転送を介してメッセージを中継して検出を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad731-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="ad731-111">これらのシナリオでは、影響を受ける Microsoft 365 データセンター サーバーの IP アドレスがサード パーティ製のブロック リストに表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="ad731-112">これらのブロック リストを使用する送信先の電子メール組織は、それらのメッセージ ソースからの電子メールを拒否します。</span><span class="sxs-lookup"><span data-stu-id="ad731-112">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="ad731-113">危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="ad731-113">High-risk delivery pool</span></span>
<span data-ttu-id="ad731-114">これを防止するために、スパムと判断された、またはサービスまたは送信スパム ポリシーの送信制限を超えている Microsoft 365 データセンター サーバー [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)からのすべての送信 [](configure-the-outbound-spam-policy.md)メッセージは、リスクの高い配信プール経由で送信 _されます。_</span><span class="sxs-lookup"><span data-stu-id="ad731-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="ad731-115">高リスク配信プールは、"低品質" メッセージ (スパムやバックスカターなど) の送信にのみ使用される送信電子メール用の個別の IP アドレス [プールです](backscatter-messages-and-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="ad731-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="ad731-116">危険度の高い配信プールを使用すると、送信電子メールの通常の IP アドレス プールがスパムを送信するのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad731-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="ad731-117">送信電子メールの通常の IP アドレス プールは、"高品質" メッセージを送信する評判を維持します。このため、これらの IP アドレスが IP ブロック リストに表示される可能性が低く抑わります。</span><span class="sxs-lookup"><span data-stu-id="ad731-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="ad731-118">リスクの高い配信プール内の IP アドレスが IP ブロック リストに配置される可能性は非常に高いですが、これは設計上の理由です。</span><span class="sxs-lookup"><span data-stu-id="ad731-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="ad731-119">多くの電子メール組織は危険度の高い配信プールからのメッセージを受け入れないので、目的の受信者への配信は保証されません。</span><span class="sxs-lookup"><span data-stu-id="ad731-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="ad731-120">詳細については、「送信スパム [を制御する」を参照してください](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="ad731-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ad731-121">送信元の電子メール ドメインに A レコードがないメッセージとパブリック DNS で定義された MX レコードがないメッセージは、スパムや送信制限の廃棄に関係なく、常にリスクの高い配信プールを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ad731-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="ad731-122">バウンス メッセージ</span><span class="sxs-lookup"><span data-stu-id="ad731-122">Bounce messages</span></span>

<span data-ttu-id="ad731-123">送信の危険度の高い配信プールは、すべての配信レポート (NDRs、バウンス メッセージ、配信状態通知、または DSN とも呼ばれる) の配信を管理します。</span><span class="sxs-lookup"><span data-stu-id="ad731-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="ad731-124">次のような、NDRs の急増の原因として考えられるものがあります。</span><span class="sxs-lookup"><span data-stu-id="ad731-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="ad731-125">サービスを使用しているお客様の 1 人に影響を与えるスプーフィング キャンペーン。</span><span class="sxs-lookup"><span data-stu-id="ad731-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="ad731-126">ディレクトリの収集攻撃。</span><span class="sxs-lookup"><span data-stu-id="ad731-126">A directory harvest attack.</span></span>
- <span data-ttu-id="ad731-127">スパム攻撃。</span><span class="sxs-lookup"><span data-stu-id="ad731-127">A spam attack.</span></span>
- <span data-ttu-id="ad731-128">不正な電子メール サーバー。</span><span class="sxs-lookup"><span data-stu-id="ad731-128">A rogue email server.</span></span>

<span data-ttu-id="ad731-129">これらの問題はすべて、サービスによって処理されるNDRs の数が突然増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="ad731-130">多くの場合、これらの NDRs は、他の電子メール サーバーやサービス (バックスカターとも呼ばれる) に対するスパム _[のように見なされます](backscatter-messages-and-eop.md)_。</span><span class="sxs-lookup"><span data-stu-id="ad731-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="ad731-131">中継プール</span><span class="sxs-lookup"><span data-stu-id="ad731-131">Relay pool</span></span>

<span data-ttu-id="ad731-132">Microsoft 365 から転送または中継されるメッセージは、特別な中継プールを使用して送信されます。最終的な送信先では、Microsoft 365 を実際の送信者と見なす必要はなだからです。</span><span class="sxs-lookup"><span data-stu-id="ad731-132">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="ad731-133">また、Microsoft 365 からメールを自動送信または中継する正当で無効なシナリオが考えられます。このため、このトラフィックを分離することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ad731-133">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="ad731-134">危険度の高い配信プールと同様に、中継されたメールには別の IP アドレス プールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad731-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="ad731-135">このアドレス プールは頻繁に変更される可能性が高く、公開されません。</span><span class="sxs-lookup"><span data-stu-id="ad731-135">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="ad731-136">Microsoft 365 では、転送されたメッセージを自信を持って配信できるよう、元の送信者が正当な送信者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="ad731-137">これを行うには、電子メール認証 (SPF、DKIM、DMARC) がメッセージに届く際にパスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad731-137">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="ad731-138">送信者を認証できる場合は、送信者書き換えを使用して、転送されたメッセージが信頼できる送信元からのメッセージであるのを受信者が把握するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad731-138">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="ad731-139">このしくみと、送信者書き換えスキーム [(SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)で送信側ドメインが認証に合格した場合の確認方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad731-139">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
