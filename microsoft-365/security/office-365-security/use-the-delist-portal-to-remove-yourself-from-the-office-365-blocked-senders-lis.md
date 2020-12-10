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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: この記事では、リストから除外ポータルを使用して、Microsoft 365 の受信拒否リストから自分自身を削除する方法について説明します。
ms.openlocfilehash: 0c87d467db004a50502402b05eb0fa3283aa46c5
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614764"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>無効化ポータルを使って、受信拒否リストから自分自身を削除する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Microsoft 365 に電子メールアドレスがある受信者に電子メールを送信しようとすると、エラーメッセージが表示されますか。 エラーメッセージを受信しないようにする必要がある場合は、リストから除外ポータルを使用して、受信拒否リストから自分自身を削除することができます。

## <a name="what-is-the-blocked-senders-list"></a>受信拒否リストとは何ですか。

Microsoft は、受信拒否リストを使って、スパム、スプーフィング、フィッシング攻撃からお客様を保護しています。 メールサーバーの IP アドレス (メールサーバーがインターネット上で自分自身を識別するために使用するアドレス) は、さまざまな理由の1つとして、Microsoft 365 に対する潜在的な脅威としてタグ付けされました。 Microsoft 365 によって IP アドレスが一覧に追加されると、その ip アドレスとお客様との間のすべての通信がデータセンターによって妨げられます。

メール メッセージに対して、次のようなエラーが含まれた応答を受信する場合、お客様は受信拒否リストに追加されています。

> 550 5.7.606-649 アクセス拒否、禁止された送信 IP [_ip address_]、このリストからの削除を要求するには、にアクセスして <https://sender.office.com/> 、指示に従ってください。 詳細については、「 [Exchange Online のメール配信不能レポート](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)」を参照してください。

ここで、 _IP address_ は、メール サーバーを稼働しているコンピューターの IP アドレスです。

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>リストから除外ポータルを使用して、受信拒否リストから自分自身を削除するには

1. Web ブラウザーで、<https://sender.office.com> に移動します。

2. ページ上の指示に従います。エラー メッセージを受信したメール アドレス、エラー メッセージで特定されている IP アドレスを使っていることを確認してください。1 回のアクセスにつき、1 つのメール アドレス、1 つの IP アドレスのみ入力できます。

3. [ **保存**] をクリックします。

    ポータルは、指定したメール アドレスにメールを送信します。 電子メールは次のようになります。リストから除外 ![ ポータルを通じて要求を送信したときに受信された電子メールのスクリーンショット](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. リストから除外のポータルから受信したメールの中にある確認のリンクをクリックします。

    これで、リストから除外のポータルに戻ります。

5. リストから除外のポータルで **[IP をリストから除外]** をクリックします。

    受信拒否リストから IP アドレスが削除されると、その IP アドレスからの電子メールメッセージは、Microsoft 365 を使用している受信者に配信されます。 そのため、その IP アドレスから送信された電子メールが不適切または悪意のあるものにならないようにしてください。それ以外の場合は、IP アドレスが再度ブロックされることがあります。

    > [!NOTE]
    > 最大24時間かかる場合があります。制限が削除されるまでに、結果が大幅に異なる場合があります。

IP がブロックされないようにするには、「 [Create safe sender lists IN EOP](create-safe-sender-lists-in-office-365.md) and [Outbound SPAM protection in EOP](outbound-spam-controls.md) 」を参照してください。
