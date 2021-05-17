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
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599913"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="d91a3-103">送信方向の配信のプール</span><span class="sxs-lookup"><span data-stu-id="d91a3-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d91a3-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="d91a3-104">**Applies to**</span></span>
- [<span data-ttu-id="d91a3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d91a3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d91a3-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="d91a3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d91a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d91a3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d91a3-108">データセンター内のMicrosoft 365サーバーは、スパムの送信を一時的に有罪にしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d91a3-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="d91a3-109">たとえば、オンプレミスの電子メール組織でマルウェアや悪意のあるスパム攻撃が発生し、Microsoft 365アカウントを介して送信Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="d91a3-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="d91a3-110">攻撃者は、転送を介してメッセージを中継して検出Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="d91a3-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="d91a3-111">これらのシナリオでは、影響を受けるデータセンター サーバーの IP Microsoft 365サード パーティのブロックリストに表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d91a3-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="d91a3-112">これらのブロックリストを使用する宛先電子メール組織は、これらのメッセージ ソースからの電子メールを拒否します。</span><span class="sxs-lookup"><span data-stu-id="d91a3-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="d91a3-113">リスクの高い配信プール</span><span class="sxs-lookup"><span data-stu-id="d91a3-113">High-risk delivery pool</span></span>
<span data-ttu-id="d91a3-114">これを防止するために、スパムと判断された、またはサービスまたは送信スパム ポリシーの送信制限を超えている Microsoft 365 データセンター サーバーからの送信メッセージはすべて [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)、リスクの [](configure-the-outbound-spam-policy.md)高い配信プールを介して _送信されます_。</span><span class="sxs-lookup"><span data-stu-id="d91a3-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="d91a3-115">リスクの高い配信プールは、"低品質" メッセージ (スパムやバックスカッターなど) の送信にのみ使用される送信メール用の個別の IP アドレス [プールです](backscatter-messages-and-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="d91a3-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="d91a3-116">リスクの高い配信プールを使用すると、送信メールの通常の IP アドレス プールがスパムを送信するのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d91a3-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="d91a3-117">送信電子メールの通常の IP アドレス プールは、"高品質" メッセージを送信する評判を維持し、IP ブロックリストにこれらの IP アドレスが表示される可能性を低減します。</span><span class="sxs-lookup"><span data-stu-id="d91a3-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="d91a3-118">リスクの高い配信プール内の IP アドレスが IP ブロックリストに配置される可能性は非常に高いですが、これは設計上です。</span><span class="sxs-lookup"><span data-stu-id="d91a3-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="d91a3-119">多くの電子メール組織がリスクの高い配信プールからのメッセージを受け入れないので、目的の受信者への配信は保証されません。</span><span class="sxs-lookup"><span data-stu-id="d91a3-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="d91a3-120">詳細については、「送信スパムを [制御する」を参照してください](outbound-spam-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="d91a3-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d91a3-121">送信元メール ドメインに A レコードがないメッセージと、パブリック DNS で定義されている MX レコードがないメッセージは、スパムや送信制限の廃棄に関係なく、常にリスクの高い配信プールを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d91a3-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="d91a3-122">バウンス メッセージ</span><span class="sxs-lookup"><span data-stu-id="d91a3-122">Bounce messages</span></span>

<span data-ttu-id="d91a3-123">送信リスクの高い配信プールは、すべての配信不可レポート (NDRs、バウンス メッセージ、配信状態通知、または DSN とも呼ばれる) の配信を管理します。</span><span class="sxs-lookup"><span data-stu-id="d91a3-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="d91a3-124">NDRs の急増の原因としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="d91a3-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="d91a3-125">サービスを使用しているユーザーの 1 人に影響を与えるスプーフィング キャンペーン。</span><span class="sxs-lookup"><span data-stu-id="d91a3-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="d91a3-126">ディレクトリハーベスト攻撃。</span><span class="sxs-lookup"><span data-stu-id="d91a3-126">A directory harvest attack.</span></span>
- <span data-ttu-id="d91a3-127">スパム攻撃。</span><span class="sxs-lookup"><span data-stu-id="d91a3-127">A spam attack.</span></span>
- <span data-ttu-id="d91a3-128">不正なメール サーバー。</span><span class="sxs-lookup"><span data-stu-id="d91a3-128">A rogue email server.</span></span>

<span data-ttu-id="d91a3-129">これらの問題はすべて、サービスによって処理されるNDRsの数が急激に増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d91a3-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="d91a3-130">多くの場合、これらのNDRsは、他の電子メール サーバーやサービス _[(backscatter](backscatter-messages-and-eop.md)_ とも呼ばれる) へのスパムのように見える。</span><span class="sxs-lookup"><span data-stu-id="d91a3-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
