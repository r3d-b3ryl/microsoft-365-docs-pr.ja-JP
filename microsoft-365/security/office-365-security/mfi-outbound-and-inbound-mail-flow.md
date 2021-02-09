---
title: メール フロー ダッシュボードでの送信および受信メール フローの分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理者は、セキュリティ/コンプライアンス センターのメール フロー ダッシュボードで、送信メール フローと受信メール フロー&確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fcce6981369217f21ace5fdf2abbf23ca8606569
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150810"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a><span data-ttu-id="0be21-103">セキュリティ/コンプライアンス センターでの送信および受信メール フロー&分析情報</span><span class="sxs-lookup"><span data-stu-id="0be21-103">Outbound and inbound mail flow insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0be21-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0be21-104">**Applies to**</span></span>
- [<span data-ttu-id="0be21-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0be21-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="0be21-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0be21-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="0be21-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0be21-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="0be21-108">セキュリティ & コンプライアンス センターのメール フロー [](mail-flow-insights-v2.md)ダッシュボードの送信および [](https://protection.office.com)受信メール フローの分析情報は、[コネクタ](view-mail-flow-reports.md#connector-report)レポートと以前の **TLS** 概要レポートからの情報を 1 か所で結合します。</span><span class="sxs-lookup"><span data-stu-id="0be21-108">The **Outbound and inbound mail flow** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) combines the information from the [Connector report](view-mail-flow-reports.md#connector-report) and the former **TLS overview report** in one place.</span></span>

<span data-ttu-id="0be21-109">ウィジェットは、メッセージが組織との間で配信される場合に接続に使用される TLS 暗号化を表示します。</span><span class="sxs-lookup"><span data-stu-id="0be21-109">The widget displays the TLS encryption that's used for the connection when messages are delivered to and from your organization.</span></span> <span data-ttu-id="0be21-110">他の電子メール サービスとの接続は、TLS が両側で提供される場合に TLS によって暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="0be21-110">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="0be21-111">ウィジェットは、メール フローの最後の週のスナップショットを提供します。</span><span class="sxs-lookup"><span data-stu-id="0be21-111">The widget offers a snapshot of the last week of mail flow.</span></span>

![Security & Compliance Center のメール フロー ダッシュボードの送信および受信メール フロー ウィジェット](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

<span data-ttu-id="0be21-113">ウィジェットの情報は、Microsoft 365 のコネクタと TLS メッセージ保護に関連しています。</span><span class="sxs-lookup"><span data-stu-id="0be21-113">The information in the widget is related to connectors and TLS message protection in Microsoft 365.</span></span> <span data-ttu-id="0be21-114">詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0be21-114">For more information, see these topics:</span></span>

- [<span data-ttu-id="0be21-115">コネクタを使用してメール フローを構成する</span><span class="sxs-lookup"><span data-stu-id="0be21-115">Configure mail flow using connectors</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [<span data-ttu-id="0be21-116">メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0be21-116">How Exchange Online uses TLS to secure email connections</span></span>](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [<span data-ttu-id="0be21-117">Microsoft 365 での暗号化に関するテクニカル リファレンスの詳細</span><span class="sxs-lookup"><span data-stu-id="0be21-117">Technical reference details about encryption in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="0be21-118">転送中に保護されたメッセージ (TLS により)</span><span class="sxs-lookup"><span data-stu-id="0be21-118">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="0be21-119">ウィジェットの [詳細 **の** 表示] をクリックすると、転送中 **に (TLS** によって) 保護されたメッセージのフライアウトに、組織に入って出るメッセージの TLS 保護が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0be21-119">When you click **View Details** on the widget, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![送信および受信電子メール ウィジェットの [詳細の表示] をクリックした後に表示される転送中に保護されたメッセージ (TLS による) フライアウト](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

<span data-ttu-id="0be21-121">現在、TLS 1.2 は、Microsoft 365 が提供する最も安全なバージョンの TLS です。</span><span class="sxs-lookup"><span data-stu-id="0be21-121">Currently, TLS 1.2 is the most secure version of TLS that's offered by Microsoft 365.</span></span> <span data-ttu-id="0be21-122">多くの場合、コンプライアンス監査に使用されている TLS 暗号化を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="0be21-122">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="0be21-123">ほとんどの送信元および送信先の電子メール サーバーとの直接的な関係はおそらくない (ユーザーは所有していないが、Microsoft もそうしていない) ので、それらのサーバーで使用される TLS 暗号化を向上させるオプションは多くはありません。</span><span class="sxs-lookup"><span data-stu-id="0be21-123">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="0be21-124">ただし、コネクタ [を使用して](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 、電子メール サーバーと Microsoft 365 の間で送信されるメッセージに対して最適な TLS 保護を確保できます。</span><span class="sxs-lookup"><span data-stu-id="0be21-124">But, you can use [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) to ensure the best available TLS protection for messages that are sent between your email servers and Microsoft 365.</span></span> <span data-ttu-id="0be21-125">Microsoft 365 とパートナーに属する独自の電子メール サーバーまたはサーバー間のメール フローは、通常のメッセージよりも重要で機密性が高い場合が多いので、これらのメッセージに対して追加のセキュリティと影響を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0be21-125">Mail flow between Microsoft 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span>

<span data-ttu-id="0be21-126">独自の電子メール サーバーをアップグレードまたは修正して、使用されている TLS 暗号化を向上させるか、パートナーに連絡して同じことを行います。</span><span class="sxs-lookup"><span data-stu-id="0be21-126">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="0be21-127">コネクタ **レポートには、Microsoft** 365 コネクタを使用するメッセージのメール フロー ボリュームと TLS 暗号化の両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0be21-127">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Microsoft 365 connectors.</span></span>

<span data-ttu-id="0be21-128">コネクタ レポートリンク **をクリックすると** 、コネクタ レポートに [移動できます](view-mail-flow-reports.md#connector-report)。</span><span class="sxs-lookup"><span data-stu-id="0be21-128">You can click the **Connector report** link to go to the [Connector report](view-mail-flow-reports.md#connector-report).</span></span> <span data-ttu-id="0be21-129">関連する条件が検出された場合は、 **コネクタ** レポート ページで次の分析情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0be21-129">The following insights might be available on the **Connector report** page if the associated condition has been detected:</span></span>

- <span data-ttu-id="0be21-130">**受信パートナー コネクタに重大な TLS1.0 メール フローが表示される**</span><span class="sxs-lookup"><span data-stu-id="0be21-130">**Inbound Partner connector seeing significant TLS1.0 mail flow**</span></span>
- <span data-ttu-id="0be21-131">**重要な TLS1.0 メール フローが表示される受信 OnPremises コネクタ**</span><span class="sxs-lookup"><span data-stu-id="0be21-131">**Inbound OnPremises connector seeing significant TLS1.0 mail flow**</span></span>

<span data-ttu-id="0be21-132">TLS 1.0 接続の場合、TLS 1.0 のサポートが最終的に Microsoft 365 で廃止された場合に問題を回避するには、メール サーバーまたはパートナーのサーバーをアップグレードまたは修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0be21-132">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Microsoft 365.</span></span>

## <a name="see-also"></a><span data-ttu-id="0be21-133">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="0be21-133">See also</span></span>

<span data-ttu-id="0be21-134">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="0be21-134">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
