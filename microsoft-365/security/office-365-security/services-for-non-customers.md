---
title: ユーザーにメールを送信する非顧客Microsoft 365
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
ms.openlocfilehash: 2894d565a08cf500199b123a0acd738de129faf0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174185"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>ユーザーにメールを送信する非顧客Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


電子メールの不正使用、迷惑メール、詐欺メール (フィッシング詐欺) は、引き続き電子メール エコシステム全体にとって負担となっています。 電子メールの使用に対するユーザーの信頼を維持するために、Microsoft はユーザーの保護に役立つさまざまなポリシーとテクノロジを導入しています。 ただし、正当な電子メールが不利を被らないようにするべきであることも理解しています。 そのため、送信者が送信評判を積極的に管理することで、Microsoft 365ユーザーに電子メールを配信する能力を向上させる一組のサービスを確立しました。

この概要では、お客様でない場合でも、組織に提供するメリットに関する情報を提供します。

## <a name="sender-solutions"></a>送信者のソリューション

****

|サービス|利点|
|---|---|
|このオンライン ヘルプ コンテンツ|提供内容： <ul><li>EOP ユーザーへの通信の提供に関連する質問の開始点。</li><li>ポリシーと要件を含む簡単なオンライン ガイドが含まれています。</li><li>Microsoft が採用している迷惑メール フィルターと認証テクノロジの概要。</li><ul>|
|[Microsoft サポート](#microsoft-support)|配信の問題に対するセルフヘルプと充実したサポートを提供します。|
|[スパム対策 IP リスト削除ポータル](#anti-spam-ip-delist-portal)|IP リストからの除外要求を送信するためのツール。この要求を送信する前に、送信者は、疑わしい IP から不正なメールや悪意のあるメールが送信されないことを確認する責任があります。|
|[Exchange Online からの迷惑メールの不正使用とスパムの報告](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|スパムなどの不要なメールが、インターネットやメール システムExchange Online迷惑メールから送信されるのを防きます。|
|

## <a name="microsoft-support"></a>Microsoft サポート

Microsoft では、受信者へのメールの送信に問題があるユーザー向けMicrosoft 365提供しています。 次のことをお勧めします。

- 受信するあらゆる配信不能レポートの指示に従ってください。

- 「[Office 365 に送信されるメールのトラブルシューティング](troubleshooting-mail-sent-to-office-365.md)」で、ユーザー以外が経験する一般的な問題について確認します。

- 拒否された[Microsoft 365](https://sender.office.com)リストから IP を削除する要求を送信するには、リストから削除するポータルを使用します。

- [Microsoft コミュニティ フォーラム](https://community.office365.com/f/)をご覧ください。

- 別の方法を使用してメールを送信しようとしている顧客に連絡し、Microsoft サポートに連絡し、代わりにサポート チケットを開く必要があります。 場合によっては、Microsoft サポートは法的な理由から、ブロックされている IP 領域を所有している送信者と直接やり取りする必要が生じます。 ただし通常は、ユーザー以外はサポート チケットをオープンできません。

  Office 365 の Microsoft 製品サポートについて詳しくは、「 [サポート](/office365/servicedescriptions/office-365-platform-service-description/support)」をご覧ください。

## <a name="anti-spam-ip-delist-portal"></a>スパム対策 IP リスト削除ポータル

これは、ブロックされた送信者リストから自分自身を削除するために使用Microsoft 365セルフサービス ポータルです。 Microsoft 365 に電子メール アドレスが含まれる受信者に電子メールを送信しようとするときにエラー メッセージが表示される場合は、このポータルを使用します。 詳細については、「[リストから除外ポータルを使って、受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)」を参照してください。

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Exchange Online からの迷惑メールの不正使用とスパムの報告

場合Microsoft 365の使用条件およびポリシーに違反して、第三者が迷惑メールを送信するために使用することがあります。 ユーザーから迷惑メールを受けOffice 365、これらのメッセージを Microsoft に報告できます。 手順については、「メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。