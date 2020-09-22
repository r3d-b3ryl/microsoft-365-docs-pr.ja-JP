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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 電子メールをユーザーが安心して使用できるようにするため、Microsoft は各種ポリシーやテクノロジを用いて、ユーザーを保護しています。
ms.openlocfilehash: e9389d52ee1d6c1c0bbab8630778749a6ed6005f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199579"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Microsoft 365 にメールを送信するユーザー以外のサービス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


電子メールの不正使用、迷惑メール、詐欺メール (フィッシング詐欺) は、引き続き電子メール エコシステム全体にとって負担となっています。 電子メールの使用においてユーザーの信頼を維持するために、Microsoft はさまざまなポリシーとテクノロジを用意して、ユーザーを保護しています。 ただし、正当な電子メールが不利を被らないようにするべきであることも理解しています。 そのため、送信者が送信評価をプロアクティブに管理することで、Microsoft 365 ユーザーに電子メールを配信する機能を向上させる一連のサービスを確立しています。

この概要では、お客様でない場合でも、組織に提供するメリットについて説明します。

## <a name="sender-solutions"></a>送信者のソリューション

****

|サービス|利点|
|---|---|
|このオンライン ヘルプ コンテンツ|提供内容： <br/> EOP ユーザーへの通信の配信に関連する質問の開始点。 <br/><br/> には、ポリシーと要件に関する簡単なオンラインガイドが含まれています。 <br/><br/> Microsoft によって使用されている迷惑メールフィルターと認証テクノロジの概要について説明します。|
|[Microsoft サポート](#microsoft-support)|配信の問題に対するセルフヘルプと充実したサポートを提供します。|
|[スパム対策 IP リストから除外ポータル](#anti-spam-ip-delist-portal)|IP リストからの除外要求を送信するためのツール。この要求を送信する前に、送信者は、疑わしい IP から不正なメールや悪意のあるメールが送信されないことを確認する責任があります。|
|[Exchange Online からの迷惑メールの不正使用とスパムの報告](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|スパムやその他の不要なメールが Exchange Online から送信されないようにして、インターネットやメールシステムを雑然としないようにします。|
|

## <a name="microsoft-support"></a>Microsoft サポート

Microsoft は、Microsoft 365 の受信者にメールを送信する際に問題が発生しているユーザーに対して、いくつかのサポートオプションを提供 次のことをお勧めします。

- 受信するあらゆる配信不能レポートの指示に従ってください。

- 「[Office 365 に送信されるメールのトラブルシューティング](troubleshooting-mail-sent-to-office-365.md)」で、ユーザー以外が経験する一般的な問題について確認します。

- [Microsoft 365 リストから除外ポータル](https://sender.office.com)を使用して、ブロックする送信者のリストから IP を削除する要求を送信します。

- [Microsoft コミュニティ フォーラム](https://community.office365.com/f/)をご覧ください。

- 別の方法を使用してメールを送信しようとしているお客様にお問い合わせください。また、Microsoft サポートに連絡して、お客様の代わりにサポートチケットを開くように依頼してください。 場合によっては、Microsoft サポートは法的な理由から、ブロックされている IP 領域を所有している送信者と直接やり取りする必要が生じます。 ただし通常は、ユーザー以外はサポート チケットをオープンできません。

  Office 365 の Microsoft 製品サポートについて詳しくは、「 [サポート](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)」をご覧ください。

## <a name="anti-spam-ip-delist-portal"></a>スパム対策 IP リストから除外ポータル

これは、Microsoft 365 の受信拒否リストから自分自身を削除するために使用できるセルフサービスポータルです。 Microsoft 365 に電子メールアドレスが含まれている受信者に電子メールを送信しようとしたときにエラーメッセージが表示される場合は、このポータルを使用します。 詳細については、「[リストから除外ポータルを使って、受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)」を参照してください。

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Exchange Online からの迷惑メールの不正使用とスパムの報告

Microsoft365 は、使用条件およびポリシーに違反して、迷惑メールを送信するためにサードパーティによって使用される場合があります。 Office 365 から迷惑メールを受信した場合は、これらのメッセージを Microsoft に報告できます。 手順については、「 [Microsoft にメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。
