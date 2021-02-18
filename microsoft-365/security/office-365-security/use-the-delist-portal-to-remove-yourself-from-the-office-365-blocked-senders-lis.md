---
title: 受信拒否リストから自分自身を削除する
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
description: この記事では、リストから削除ポータルを使用して、Microsoft 365 の受信拒否リストから自分自身を削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c11fced30ef52315ecb44dda51e6825d36b57c7e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287523"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>無効化ポータルを使って、受信拒否リストから自分自身を削除する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 365 のメール アドレスを持つ受信者に電子メールを送信しようとするときにエラー メッセージが表示される場合 エラー メッセージを受け取る必要はないと思う場合は、リストから削除ポータルを使用して、受信拒否リストから自分自身を削除できます。

## <a name="what-is-the-blocked-senders-list"></a>受信拒否リストとは

Microsoft は、受信拒否リストを使って、スパム、スプーフィング、フィッシング攻撃からお客様を保護しています。 メール サーバーの IP アドレス、つまり、メール サーバーがインターネット上で自身を識別するために使用するアドレスは、さまざまな理由から Microsoft 365 に対する潜在的な脅威としてタグ付けされています。 Microsoft 365 が IP アドレスをリストに追加すると、データセンターを通じて IP アドレスとすべてのお客様との間のすべての通信が防止されます。

メール メッセージに対して、次のようなエラーが含まれた応答を受信する場合、お客様は受信拒否リストに追加されています。

> 550 5.7.606-649 アクセスが拒否され、IP [ IP アドレス] の送信 _が禁止_ されました。この一覧からの削除を要求するには、指示に従 <https://sender.office.com/> ってアクセスしてください。 詳細については [、「Exchange Online のメール配信不可レポート」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)。

ここで、 _IP address_ は、メール サーバーを稼働しているコンピューターの IP アドレスです。

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>リストから削除ポータルを使用して、受信拒否リストから自分自身を削除するには

1. Web ブラウザーで、<https://sender.office.com> に移動します。

2. ページ上の指示に従います。エラー メッセージを受信したメール アドレス、エラー メッセージで特定されている IP アドレスを使っていることを確認してください。1 回のアクセスにつき、1 つのメール アドレス、1 つの IP アドレスのみ入力できます。

3. [ **保存**] をクリックします。

    ポータルは、指定したメール アドレスにメールを送信します。 メールは次のようになります:リストから要求を送信すると受信したメールの ![ スクリーンショット](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. リストから除外のポータルから受信したメールの中にある確認のリンクをクリックします。

    これで、リストから除外のポータルに戻ります。

5. リストから除外のポータルで **[IP をリストから除外]** をクリックします。

    IP アドレスが受信拒否リストから削除されると、その IP アドレスからの電子メール メッセージは、Microsoft 365 を使用する受信者に配信されます。 そのため、その IP アドレスから送信された電子メールが不正または悪意のあるものにならないと確信してください。そうしないと、IP アドレスが再度ブロックされる可能性があります。

    > [!NOTE]
    > 最大 24 時間かかる場合や、制限が解除される前に結果が大きく異なる場合があります。

IP [がブロックされるのを防ぐには、「EOP](create-safe-sender-lists-in-office-365.md) で差出人セーフ リストを作成する」および [「EOP](outbound-spam-controls.md) での送信スパム保護」を参照してください。
