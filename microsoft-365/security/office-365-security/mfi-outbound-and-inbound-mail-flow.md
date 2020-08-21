---
title: メール フロー ダッシュボードの送信と受信のメール フロー分析情報
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
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理者は、セキュリティグループ ポリシー のメール フロー ダッシュボードで、送信と受信のメール フローのインサイトについて&できます。
ms.openlocfilehash: 920c1212f4d6dee508704c93272e48140e199710
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826895"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="5d7bf-103">コンプライアンス センターの送信と受信のメール &分析情報</span><span class="sxs-lookup"><span data-stu-id="5d7bf-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

<span data-ttu-id="5d7bf-104">セキュリティ & コンプライアンス**センターのメール フロー ダッシュボードの**送信[Mail flow dashboard](mail-flow-insights-v2.md)と受信のメール フローのインサイトでは、コネクタ レポートからの[Connector report](view-mail-flow-reports.md#connector-report)情報と、元の**TLS**概要レポートを 1 かの場所で結合します。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-104">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="5d7bf-105">このウィジェットには、組織との間でメッセージが配信されたときの接続に使用される TLS 暗号化が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-105">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="5d7bf-106">他のメール サービスと確立される接続は、両方の側側で TLS が提供されている場合に TLS によって暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-106">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="5d7bf-107">ウィジェットは、過去 1 週間のメール フローのスナップショットを提供します。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-107">The widget offers a snapshot of the last week of mail flow.</span></span>

![セキュリティ コンプライアンス センターのメール フロー ダッシュボードの送信と受信のメール フロー ウィ& ウィジェット](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="5d7bf-109">ウィジェット内の情報は、Microsoft 365 のコネクタと TLS メッセージ保護に関連しています。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-109">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="5d7bf-110">詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-110">For more information, see these topics:</span></span>

- [<span data-ttu-id="5d7bf-111">コネクタを使用してメール フローを構成する</span><span class="sxs-lookup"><span data-stu-id="5d7bf-111">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="5d7bf-112">Exchange Online が TLS を使ってメール接続をセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="5d7bf-112">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="5d7bf-113">Microsoft 365 の暗号化についてのテクニカル リファレンスの詳細</span><span class="sxs-lookup"><span data-stu-id="5d7bf-113">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="5d7bf-114">送信中に保護されたメッセージ (TLS 別)</span><span class="sxs-lookup"><span data-stu-id="5d7bf-114">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="5d7bf-115">ウィジェ **ットの [詳細** の表示] をクリックすると、 **送信中に保護されたメッセージ (TLS で保護)** ポップアップに、組織が出入りするメッセージの TLS 保護が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-115">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![[送信および受信メール ウィジェットの詳細を表示] をクリックした後に表示される、送信中 (TLS) ポップアップで保護されているメッセージ](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="5d7bf-117">現在、TLS 1.2 は Microsoft 365 が提供する TLS の中で最も安全なバージョンです。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-117">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="5d7bf-118">多くの場合、コンプライアンス監査に使用される TLS 暗号化を知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-118">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="5d7bf-119">送信元と宛先のほとんどの電子メール サーバーとの間には直接の関係がない可能性があるため (所有していないが Microsoft もしまっていない)、これらのサーバーで使用される TLS 暗号化を改善するオプションは多数ありません。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-119">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="5d7bf-120">しかし、電子メール サーバー [と](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) Microsoft 365 の間で送信されるメッセージに対して利用可能な TLS 保護を確実にするためにコネクタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-120">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="5d7bf-121">Microsoft 365 とパートナーに属している独自の電子メール サーバーやサーバー間のメール フローは通常のメッセージよりも重要かつ機密性の高いため、これらのメッセージには追加のセキュリティとアクセス性を適用したいと考えないでください。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-121">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="5d7bf-122">使用中の TLS 暗号化の向上のために独自のメール サーバーをアップグレードまたは修正したり、パートナーに同じ操作を行ってもらう場合があります。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-122">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="5d7bf-123">コネクタ **レポートには** 、Microsoft 365 コネクタを使用するメッセージのメール フロー ボリュームと TLS 暗号化の両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-123">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="5d7bf-124">コネクタ レポート リンク **をクリックして、** コネクタ レポートに [移動できます](view-mail-flow-reports.md#connector-report)。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-124">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="5d7bf-125">関連する条件が検出された場合は、[コネクタ レポート] **ページで** 次の分析情報が使用可能となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-125">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="5d7bf-126">**受信パートナー コネクタで、TLS1.0 の重要なメール フローが表示されている**</span><span class="sxs-lookup"><span data-stu-id="5d7bf-126">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="5d7bf-127">**受信 OnPremises コネクタに関する、大幅な TLS1.0 メール フローが表示されている**</span><span class="sxs-lookup"><span data-stu-id="5d7bf-127">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="5d7bf-128">TLS 1.0 接続の場合、Microsoft 365 で TLS 1.0 のサポートが最終的に廃止された場合でも問題が発生しないように、電子メール サーバーまたはパートナーのサーバーをアップグレードまたは修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-128">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d7bf-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d7bf-129">See also</span></span>

<span data-ttu-id="5d7bf-130">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="5d7bf-130">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
