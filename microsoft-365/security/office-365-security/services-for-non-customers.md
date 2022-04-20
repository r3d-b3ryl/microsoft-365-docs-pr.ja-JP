---
title: Microsoft 365にメールを送信する非顧客向けサービス
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 電子メールをユーザーが安心して使用できるようにするため、Microsoft は各種ポリシーやテクノロジを用いて、ユーザーを保護しています。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80eff003ec75eba68d1b194fe83d216fa2d013c0
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64974193"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Microsoft 365にメールを送信する非顧客向けサービス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

電子メールの不正使用、迷惑メール、詐欺メール (フィッシング詐欺) は、引き続き電子メール エコシステム全体にとって負担となっています。 Microsoft では、電子メールの使用に対するユーザーの信頼を維持するために、ユーザーの保護に役立つさまざまなポリシーとテクノロジを用意しています。 ただし、正当な電子メールが不利を被らないようにするべきであることも理解しています。 そのため、送信者が送信の評判をプロアクティブに管理することで、Microsoft 365 ユーザーに電子メールを配信する機能を向上させるための一連のサービスを確立しました。

この概要では、お客様ではない場合でも、組織に提供する特典に関する情報を提供します。

## <a name="sender-solutions"></a>送信者のソリューション

|サービス|利点|
|---|---|
|このオンライン ヘルプ コンテンツ|提供内容： <ul><li>EOP ユーザーへの通信の配信に関する質問の開始点。</li><li>ポリシーと要件に関する簡単なオンライン ガイドが含まれています。</li><li>Microsoft が採用する迷惑メール フィルターと認証テクノロジの概要。</li><ul>|
|[Microsoft サポート](#microsoft-support)|配信の問題に対するセルフヘルプと充実したサポートを提供します。|
|[スパム対策 IP のリスト解除ポータル](#anti-spam-ip-delist-portal)|IP リストからの除外要求を送信するためのツール。この要求を送信する前に、送信者は、疑わしい IP から不正なメールや悪意のあるメールが送信されないことを確認する責任があります。|
|[Exchange Online からの迷惑メールの不正使用とスパムの報告](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|スパムやその他の不要なメールがExchange Onlineから送信され、インターネットとメール システムが乱雑にならないようにします。|

## <a name="microsoft-support"></a>Microsoft サポート

Microsoft では、Microsoft 365受信者へのメールの送信に問題があるユーザー向けに、いくつかのサポート オプションを提供しています。 次のことをお勧めします。

- 受信するあらゆる配信不能レポートの指示に従ってください。

- 「[Office 365 に送信されるメールのトラブルシューティング](troubleshooting-mail-sent-to-office-365.md)」で、ユーザー以外が経験する一般的な問題について確認します。

- [Microsoft 365リスト解除ポータル](https://sender.office.com)を使用して、IP をブロックされた送信者の一覧から削除する要求を送信します。

- [Microsoft コミュニティ フォーラム](https://community.office365.com/f/)をご覧ください。

- 別の方法でメールを送信しようとしている顧客に連絡し、Microsoft サポートに連絡し、サポート チケットを開くように依頼します。 場合によっては、Microsoft サポートは法的な理由から、ブロックされている IP 領域を所有している送信者と直接やり取りする必要が生じます。 ただし通常は、ユーザー以外はサポート チケットをオープンできません。

  Office 365 の Microsoft 製品サポートについて詳しくは、「 [サポート](/office365/servicedescriptions/office-365-platform-service-description/support)」をご覧ください。

## <a name="anti-spam-ip-delist-portal"></a>スパム対策 IP のリスト解除ポータル

これは、Microsoft 365ブロックされた送信者の一覧から自分を削除するために使用できるセルフサービス ポータルです。 メール アドレスがMicrosoft 365されている受信者に電子メールを送信しようとしたときにエラー メッセージが表示され、自分がそうである必要がないと思われる場合は、このポータルを使用します。 詳細については、「[リストから除外ポータルを使って、受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)」を参照してください。

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Exchange Online からの迷惑メールの不正使用とスパムの報告

Microsoft 365は、使用条件とポリシーに違反して、迷惑メールを送信するためにサード パーティによって使用されることがあります。 Office 365から迷惑メールが届く場合は、これらのメッセージを Microsoft に報告できます。 手順については、「 [メッセージとファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。
