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
description: 配信プールを使用して、データ センター内の電子メール サーバーの評判を保護するMicrosoft 365します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c5881b20eaed8387988d01b69a4acd022c5924a2
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409142"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="8f750-103">送信方向の配信のプール</span><span class="sxs-lookup"><span data-stu-id="8f750-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8f750-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="8f750-104">**Applies to**</span></span>
- [<span data-ttu-id="8f750-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8f750-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8f750-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="8f750-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8f750-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f750-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8f750-108">データセンター内のMicrosoft 365サーバーは、スパムの送信を一時的に有罪にしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f750-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="8f750-109">たとえば、オンプレミスの電子メール組織でマルウェアや悪意のあるスパム攻撃が発生し、Microsoft 365アカウントを介して送信Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="8f750-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="8f750-110">攻撃者は、転送を介してメッセージを中継して検出Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="8f750-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="8f750-111">これらのシナリオでは、影響を受けるデータセンター サーバーの IP Microsoft 365サード パーティのブロックリストに表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f750-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="8f750-112">これらのブロックリストを使用する宛先電子メール組織は、これらのメッセージ ソースからの電子メールを拒否します。</span><span class="sxs-lookup"><span data-stu-id="8f750-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="8f750-113">リスクの高い配信プール</span><span class="sxs-lookup"><span data-stu-id="8f750-113">High-risk delivery pool</span></span>
<span data-ttu-id="8f750-114">これを防止するために、スパムと判断された、またはサービスまたは送信スパム ポリシーの送信制限を超えている Microsoft 365 データセンター サーバーからの送信メッセージはすべて [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)、リスクの [](configure-the-outbound-spam-policy.md)高い配信プールを介して _送信されます_。</span><span class="sxs-lookup"><span data-stu-id="8f750-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="8f750-115">リスクの高い配信プールは、"低品質" メッセージ (スパムやバックスカッターなど) の送信にのみ使用される送信メール用の個別の IP アドレス [プールです](backscatter-messages-and-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="8f750-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="8f750-116">リスクの高い配信プールを使用すると、送信メールの通常の IP アドレス プールがスパムを送信するのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8f750-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="8f750-117">送信電子メールの通常の IP アドレス プールは、"高品質" メッセージを送信する評判を維持し、IP ブロックリストにこれらの IP アドレスが表示される可能性を低減します。</span><span class="sxs-lookup"><span data-stu-id="8f750-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="8f750-118">リスクの高い配信プール内の IP アドレスが IP ブロックリストに配置される可能性は非常に高いですが、これは設計上です。</span><span class="sxs-lookup"><span data-stu-id="8f750-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="8f750-119">多くの電子メール組織がリスクの高い配信プールからのメッセージを受け入れないので、目的の受信者への配信は保証されません。</span><span class="sxs-lookup"><span data-stu-id="8f750-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="8f750-120">詳細については、「送信スパムを [制御する」を参照してください](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="8f750-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8f750-121">送信元メール ドメインに A レコードがないメッセージと、パブリック DNS で定義されている MX レコードがないメッセージは、スパムや送信制限の廃棄に関係なく、常にリスクの高い配信プールを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="8f750-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="8f750-122">バウンス メッセージ</span><span class="sxs-lookup"><span data-stu-id="8f750-122">Bounce messages</span></span>

<span data-ttu-id="8f750-123">送信リスクの高い配信プールは、すべての配信不可レポート (NDRs、バウンス メッセージ、配信状態通知、または DSN とも呼ばれる) の配信を管理します。</span><span class="sxs-lookup"><span data-stu-id="8f750-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="8f750-124">NDRs の急増の原因としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="8f750-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="8f750-125">サービスを使用しているユーザーの 1 人に影響を与えるスプーフィング キャンペーン。</span><span class="sxs-lookup"><span data-stu-id="8f750-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="8f750-126">ディレクトリハーベスト攻撃。</span><span class="sxs-lookup"><span data-stu-id="8f750-126">A directory harvest attack.</span></span>
- <span data-ttu-id="8f750-127">スパム攻撃。</span><span class="sxs-lookup"><span data-stu-id="8f750-127">A spam attack.</span></span>
- <span data-ttu-id="8f750-128">不正なメール サーバー。</span><span class="sxs-lookup"><span data-stu-id="8f750-128">A rogue email server.</span></span>

<span data-ttu-id="8f750-129">これらの問題はすべて、サービスによって処理されるNDRsの数が急激に増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f750-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="8f750-130">多くの場合、これらのNDRsは、他の電子メール サーバーやサービス _[(backscatter](backscatter-messages-and-eop.md)_ とも呼ばれる) へのスパムのように見える。</span><span class="sxs-lookup"><span data-stu-id="8f750-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>


### <a name="relay-pool"></a><span data-ttu-id="8f750-131">リレー プール</span><span class="sxs-lookup"><span data-stu-id="8f750-131">Relay pool</span></span>

<span data-ttu-id="8f750-132">特定のシナリオで Microsoft 365 経由で転送または中継されるメッセージは、宛先が実際の送信者として Microsoft 365 を考慮しないので、特別なリレー プールを使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="8f750-132">Messages that are forwarded or relayed via Microsoft 365 in certain scenarios will be sent using a special relay pool, because the destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="8f750-133">自動転送や電子メールの自動転送やメールの転送に関する正当で無効なシナリオがMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="8f750-133">It's important for us to isolate this email traffic, because there are legitimate and invalid scenarios for auto forwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="8f750-134">リスクの高い配信プールと同様に、中継メールには別の IP アドレス プールが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f750-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="8f750-135">このアドレス プールは頻繁に変更される可能性があります。また、このアドレス プールは公開された SPF レコードの一部Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="8f750-135">This address pool is not published because it can change often, and it's not part of published SPF record for Microsoft 365.</span></span>

<span data-ttu-id="8f750-136">Microsoft 365、転送されたメッセージを自信を持って配信できるよう、元の送信者が正当なメッセージを提供することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f750-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span>

<span data-ttu-id="8f750-137">転送/中継されたメッセージは、リレー プールの使用を避けるために、次のいずれかの条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f750-137">The forwarded/relayed message should meet one of the following criteria to avoid using the relay pool:</span></span>

- <span data-ttu-id="8f750-138">送信送信者は、受け入 [れ可能なドメイン内にいます](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="8f750-138">The outbound sender is in an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
- <span data-ttu-id="8f750-139">SPF は、メッセージが送信される際にMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="8f750-139">SPF passes when the message comes to Microsoft 365.</span></span>
- <span data-ttu-id="8f750-140">送信者ドメインの DKIM は、メッセージが送信される際にMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="8f750-140">DKIM on the sender domain passes when the message comes to Microsoft 365.</span></span>
 
<span data-ttu-id="8f750-141">送信サーバー IP (中継プールは 40.95.0.0/16 の範囲になります) を見て、または送信サーバー名 (名前に "rly" が含む) を見て、リレー プールを介してメッセージが送信されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8f750-141">You can tell that a message was sent via the relay pool by looking at the outbound server IP (the relay pool will be in the 40.95.0.0/16 range), or by looking at the outbound server name (will have "rly" in the name).</span></span>

<span data-ttu-id="8f750-142">送信者を認証できる場合は、送信者書き換えスキーム (SRS) を使用して、転送されたメッセージが信頼できるソースからのメッセージである受信者の電子メール システムが知るのを支援します。</span><span class="sxs-lookup"><span data-stu-id="8f750-142">In cases where we can authenticate the sender, we use Sender Rewriting Scheme (SRS) to help the recipient email system know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="8f750-143">送信側ドメインが Office 365 の[Sender Rewriting Scheme (SRS)](/office365/troubleshoot/antispam/sender-rewriting-scheme)で認証に合格する方法と、その方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8f750-143">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>

<span data-ttu-id="8f750-144">DKIM が動作するには、ドメインの送信に DKIM を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="8f750-144">For DKIM to work, make sure you enable DKIM for sending domain.</span></span> <span data-ttu-id="8f750-145">たとえば、fabrikam.com は組織の contoso.com ドメインで定義されます。</span><span class="sxs-lookup"><span data-stu-id="8f750-145">For example, fabrikam.com is part of contoso.com and is defined in the accepted domains of the organization.</span></span> <span data-ttu-id="8f750-146">メッセージの送信者が sender@fabrikam.com 場合は、DKIM を有効にする必要 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="8f750-146">If the message sender is sender@fabrikam.com, DKIM needs to be enabled for fabrikam.com.</span></span> <span data-ttu-id="8f750-147">「DKIM を使用してカスタム ドメインから送信された送信メールを検証する」で有効にする [方法について説明します](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="8f750-147">you can read on how to enable at [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="8f750-148">カスタム ドメインを追加するには、「ドメインを追加する」の手順に[従Microsoft 365。](../../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="8f750-148">To add a custom domains follow the steps in [Add a domain to Microsoft 365](../../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="8f750-149">ドメインの MX レコードがサード パーティ のサービスまたはオンプレミスの電子メール サーバーをポイントしている場合は、コネクタの拡張フィルター [を使用する必要があります](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="8f750-149">If the MX record for your domain points to a third party service or an on-premises email server, you should use [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="8f750-150">拡張フィルターを使用すると、受信メールに対して SPF 検証が正しく、リレー プールを介した電子メールの送信を回避できます。</span><span class="sxs-lookup"><span data-stu-id="8f750-150">Enhanced Filtering ensures SPF validation is correct for inbound mail and will avoid sending email through the relay pool.</span></span>

