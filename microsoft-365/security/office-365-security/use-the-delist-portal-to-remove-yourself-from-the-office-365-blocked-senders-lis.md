---
title: 受信拒否リストから自分を削除する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: この記事では、リストから削除するポータルを使用して、受信拒否リストから自分を削除Microsoft 365について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7beee058a85d7ab44a6a4a94b362fa669537f573754de8558d713332d897843f
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "56886161"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>無効化ポータルを使って、受信拒否リストから自分自身を削除する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

電子メール アドレスが受信者に電子メールを送信しようとするときにエラー メッセージが表示Microsoft 365。 エラー メッセージを受け取る必要はないと思う場合は、リストから削除するポータルを使用して、ブロックされた送信者の一覧から自分を削除できます。

## <a name="what-is-the-blocked-senders-list"></a>ブロックされた送信者リストとは

Microsoft は、受信拒否リストを使って、スパム、スプーフィング、フィッシング攻撃からお客様を保護しています。 メール サーバーの IP アドレス 、つまり、メール サーバーがインターネット上で自分自身を識別するために使用するアドレスは、さまざまな理由の 1 つで Microsoft 365 に対する潜在的な脅威としてタグ付けされました。 IP Microsoft 365リストに追加すると、データセンターを通じて IP アドレスと任意の顧客との間のすべての通信が防止されます。

メール メッセージに対して、次のようなエラーが含まれた応答を受信する場合、お客様は受信拒否リストに追加されています。

> 550 5.7.606-649 アクセスが拒否され、IP [ IP アドレス ] の送信 _が禁止_ されています。このリストからの削除を要求するには、指示に従って <https://sender.office.com/> アクセスしてください。 詳細については、「メール配信不可[レポート」を参照Exchange Online。](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

ここで、 _IP address_ は、メール サーバーを稼働しているコンピューターの IP アドレスです。

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>ポータルのリストを削除して、ブロックされた送信者の一覧から自分を削除するには

1. Web ブラウザーで、<https://sender.office.com> に移動します。

2. ページ上の指示に従います。エラー メッセージを受信したメール アドレス、エラー メッセージで特定されている IP アドレスを使っていることを確認してください。1 回のアクセスにつき、1 つのメール アドレス、1 つの IP アドレスのみ入力できます。

3. [ **保存**] をクリックします。

    ポータルは、指定したメール アドレスにメールを送信します。 電子メールは次のようになります。削除ポータルから要求を送信するときに受信した電子メールの ![ スクリーンショット](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. リストから除外のポータルから受信したメールの中にある確認のリンクをクリックします。

    これで、リストから除外のポータルに戻ります。

5. リストから除外のポータルで **[IP をリストから除外]** をクリックします。

    IP アドレスがブロックされた送信者リストから削除されると、その IP アドレスからの電子メール メッセージは、ユーザーが使用する受信者に配信Microsoft 365。 そのため、その IP アドレスから送信された電子メールが悪用や悪意を持たなかったりしないという確信を持ってください。それ以外の場合は、IP アドレスが再度ブロックされる可能性があります。

    > [!NOTE]
    > 制限が削除される前に、最大 24 時間かかる場合や、結果が大きく異なる場合があります。

IP [がブロックされるのを防ぐには、「EOP](create-safe-sender-lists-in-office-365.md) で差出人セーフ リストを作成する」および [「EOP](outbound-spam-controls.md) の送信スパム保護」を参照してください。