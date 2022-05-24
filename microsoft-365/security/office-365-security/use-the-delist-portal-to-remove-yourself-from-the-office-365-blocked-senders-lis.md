---
title: ブロックされた送信者の一覧から自分を削除し、アドレス 5.7.511 アクセス拒否エラー
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: この記事では、リスト削除ポータルを使用して、Microsoft 365ブロックされた送信者リストから自分を削除する方法について説明します。 これは、アドレス 5.7.511 アクセス拒否エラーに対する最適な応答です。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 83822faaf1c667524dd88fc1bba400c10fa30ac3
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65647735"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list-and-address-57511-access-denied-errors"></a>リスト解除ポータルを使用して、ブロックされた送信者の一覧から自分を削除し、アドレス 5.7.511 アクセス拒否エラー

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

電子メール アドレスがMicrosoft 365されている受信者に電子メールを送信しようとすると、エラー メッセージが表示されますか (たとえば、アドレス 5.7.511 アクセスが拒否されました)。 エラー メッセージが表示されないと思われる場合は、リスト解除ポータルを使用して、ブロックされている送信者リストから自分を削除できます。

## <a name="what-is-the-blocked-senders-list"></a>ブロックされた送信者の一覧は何ですか?

Microsoft は、受信拒否リストを使って、スパム、スプーフィング、フィッシング攻撃からお客様を保護しています。 メール サーバーの IP アドレス、つまり、メール サーバーがインターネット上で自分自身を識別するために使用するアドレスは、さまざまな理由のいずれかでMicrosoft 365する潜在的な脅威としてタグ付けされました。 Microsoft 365 IP アドレスを一覧に追加すると、データセンターを通じて IP アドレスと顧客間の通信が妨げられます。

メール メッセージに対して、次のようなエラーが含まれた応答を受信する場合、お客様は受信拒否リストに追加されています。

> 550 5.7.606-649 アクセスが拒否され、IP [_IP アドレス_] の送信が禁止されました (例: 5.7.511 アクセスが拒否されました:この一覧から削除を要求するには、アクセスして指示に従ってください <https://sender.office.com/> 。 詳細については、「[Exchange Onlineで配信不能レポートを電子メールで送信](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)する」を参照してください。

ここで、 _IP address_ は、メール サーバーを稼働しているコンピューターの IP アドレスです。

## <a name="verify-senders-before-removing-them-from-the-blocked-senders-list"></a>受信拒否リストから削除する前に送信者を確認する

送信者がブロックされた送信者の一覧に表示される理由は十分にありますが、間違いが発生する可能性があります。 ブロックされた送信者とリスト解除のバランスの取れた説明については、このビデオをご覧ください。
<p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMhvD]

## <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list-after-errors-like-57511-access-denied"></a>リスト解除ポータルを使用して、ブロックされた送信者リストから自分を削除するには (5.7.511 Access denyed などのエラーの後)

1. Web ブラウザーで、<https://sender.office.com> に移動します。

2. ページ上の指示に従います。エラー メッセージを受信したメール アドレス、エラー メッセージで特定されている IP アドレスを使っていることを確認してください。1 回のアクセスにつき、1 つのメール アドレス、1 つの IP アドレスのみ入力できます。

3. [ **保存**] をクリックします。

    ポータルは、指定したメール アドレスにメールを送信します。次のようなメールです。

    :::image type="content" source="../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png" alt-text="リスト解除ポータルを使用して要求を送信したときに受信した電子メール" lightbox="../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png":::

4. リストから除外のポータルから受信したメールの中にある確認のリンクをクリックします。

    これで、リストから除外のポータルに戻ります。

5. リストから除外のポータルで **[IP をリストから除外]** をクリックします。

    IP アドレスがブロックされた送信者リストから削除されると、その IP アドレスからの電子メール メッセージが、Microsoft 365を使用する受信者に配信されます。 そのため、その IP アドレスから送信されたメールが悪用や悪意を持たないことを確認してください。それ以外の場合は、IP アドレスが再びブロックされる可能性があります。

    > [!NOTE]
    > 制限が削除されるまでに、最大 24 時間かかる場合や、結果が大きく異なる場合があります。

IP がブロックされないようにするには、「 [EOP で安全な送信者リストを作成](create-safe-sender-lists-in-office-365.md) する」と [「EOP での送信スパム保護](outbound-spam-controls.md) 」を参照してください。

### <a name="how-do-fix-error-code-57511"></a>エラー コード 5.7.511 を修正する方法

送信したメール メッセージの配信について問題がある場合、Microsoft 365 または Office 365 は差出人に通知のメールを送ります。 受信するメールは配信状態通知で、DSN またはバウンス メッセージとも呼ばれます。 最も一般的な種類は配信不能レポート (NDR) と呼ばれ、メッセージが配信されなかったことを伝えます。 特定の状況では、Microsoft は IP からのトラフィックに対して追加の調査を行う必要があります。NDR コード 5.7.511 を受け取っている場合は、リスト解除ポータルを使用 **することはできません** 。

> 550 5.7.511 アクセス拒否、禁止送信者[xxx.xxx.xxx.xxx]。 この一覧から削除を要求するには、このメッセージを delist@messaging.microsoft.com に転送します。 詳細については、次の情報を <https://go.microsoft.com/fwlink/?LinkId=526653>参照してください。

この一覧からの削除を要求する電子メールで、完全な NDR コードと IP アドレスを指定します。 Microsoft は、次の手順で 48 時間以内に連絡します。

## <a name="more-information"></a>詳細

**コンシューマー サービスである Outlook.com の** リスト解除フォームは、[こちらにあります](https://support.microsoft.com/supportrequestform/8ad563e3-288e-2a61-8122-3ba03d6b8d75)。 _提出_ の方向については、必ず [FAQ](https://sendersupport.olc.protection.outlook.com/pm/troubleshooting.aspx) を最初に読んでください。
