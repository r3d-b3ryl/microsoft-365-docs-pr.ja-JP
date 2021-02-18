---
title: Microsoft 365 にメールを送信するユーザー以外のサービス
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 電子メールをユーザーが安心して使用できるようにするため、Microsoft は各種ポリシーやテクノロジを用いて、ユーザーを保護しています。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879d2c9d3bc2af0f78a25eb1381a74b67171e939
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "50290765"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Microsoft 365 にメールを送信するユーザー以外のサービス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


電子メールの不正使用、迷惑メール、詐欺メール (フィッシング詐欺) は、引き続き電子メール エコシステム全体にとって負担となっています。 電子メールの使用に対するユーザーの信頼を維持するために、Microsoft では、ユーザーを保護するためにさまざまなポリシーとテクノロジを導入しています。 ただし、正当な電子メールが不利を被らないようにするべきであることも理解しています。 そのため、送信者が送信評価を積極的に管理して Microsoft 365 ユーザーに電子メールを配信する能力を向上させる一組のサービスを確立しました。

この概要では、お客様でない場合でも、組織に提供するメリットに関する情報を提供します。

## <a name="sender-solutions"></a>送信者のソリューション

****

|サービス|利点|
|---|---|
|このオンライン ヘルプ コンテンツ|提供内容： <ul><li>EOP ユーザーへの通信の配信に関連する質問の開始点。</li><li>ポリシーと要件を含む簡単なオンライン ガイドが含まれています。</li><li>Microsoft が採用している迷惑メール フィルターと認証テクノロジの概要。</li><ul>|
|[Microsoft サポート](#microsoft-support)|配信の問題に対するセルフヘルプと充実したサポートを提供します。|
|[スパム対策 IP リストから削除ポータル](#anti-spam-ip-delist-portal)|IP リストからの除外要求を送信するためのツール。この要求を送信する前に、送信者は、疑わしい IP から不正なメールや悪意のあるメールが送信されないことを確認する責任があります。|
|[Exchange Online からの迷惑メールの不正使用とスパムの報告](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|スパムや他の不要なメールが Exchange Online から送信され、インターネットとメール システムが乱雑になじむのを防きます。|
|

## <a name="microsoft-support"></a>Microsoft サポート

Microsoft では、Microsoft 365 受信者にメールを送信する場合に問題が発生した場合に、いくつかのサポート オプションを提供しています。 次のことをお勧めします。

- 受信するあらゆる配信不能レポートの指示に従ってください。

- 「[Office 365 に送信されるメールのトラブルシューティング](troubleshooting-mail-sent-to-office-365.md)」で、ユーザー以外が経験する一般的な問題について確認します。

- Microsoft [365](https://sender.office.com) のリストから削除されたポータルを使用して、受信拒否リストから IP を削除する要求を送信します。

- [Microsoft コミュニティ フォーラム](https://community.office365.com/f/)をご覧ください。

- 別の方法でメールを送信しようとしている顧客に連絡し、Microsoft サポートに問い合わせ、代わりにサポート チケットを開く必要があります。 場合によっては、Microsoft サポートは法的な理由から、ブロックされている IP 領域を所有している送信者と直接やり取りする必要が生じます。 ただし通常は、ユーザー以外はサポート チケットをオープンできません。

  Office 365 の Microsoft 製品サポートについて詳しくは、「 [サポート](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)」をご覧ください。

## <a name="anti-spam-ip-delist-portal"></a>スパム対策 IP リストから削除ポータル

これは、Microsoft 365 の受信拒否リストから自分自身を削除するために使用できるセルフサービス ポータルです。 このポータルは、メール アドレスが Microsoft 365 にある受信者に電子メールを送信しようとするときにエラー メッセージが表示される場合に、このポータルを使用します。 詳細については、「[リストから除外ポータルを使って、受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)」を参照してください。

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Exchange Online からの迷惑メールの不正使用とスパムの報告

Microsoft の使用条件とポリシーに違反して、サード パーティが迷惑メールを送信するために Microsoft365 を使用することがあります。 Office 365 から迷惑メールを受信した場合は、これらのメッセージを Microsoft に報告できます。 手順については、「メッセージとファイル [を Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。
