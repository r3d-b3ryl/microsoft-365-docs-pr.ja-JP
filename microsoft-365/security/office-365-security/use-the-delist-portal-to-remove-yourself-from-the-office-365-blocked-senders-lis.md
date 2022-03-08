---
title: ブロックされた送信者リストとアドレス 5.7.511 Access 拒否エラーから自分自身を削除する
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
description: この記事では、リストから削除するポータルを使用して、Microsoft 365 ブロックされた送信者リストから自分自身を削除する方法について説明します。 これは、アドレス 5.7.511 Access が拒否したエラーに対する最良の応答です。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 36187288b2a7acf1a852e6c203cbb84035ba5d7a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320243"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list-and-address-57511-access-denied-errors"></a>拒否された送信者リストとアドレス 5.7.511 Access 拒否エラーから自分を削除するには、リストから削除するポータルを使用します。

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 の電子メール アドレス (たとえば、アドレス 5.7.511 Access が拒否された) の受信者に電子メールを送信しようとするときにエラー メッセージが表示されますか? エラー メッセージを受け取る必要はないと思う場合は、リストから削除するポータルを使用して、ブロックされた送信者の一覧から自分を削除できます。

## <a name="what-is-the-blocked-senders-list"></a>ブロックされた送信者リストとは

Microsoft は、受信拒否リストを使って、スパム、スプーフィング、フィッシング攻撃からお客様を保護しています。 メール サーバーの IP アドレス 、つまり、メール サーバーがインターネット上で自分自身を識別するために使用するアドレスは、さまざまな理由の 1 つで Microsoft 365 に対する潜在的な脅威としてタグ付けされました。 Microsoft 365 が IP アドレスを一覧に追加すると、データセンターを通じて IP アドレスと任意の顧客との間のすべての通信が防止されます。

メール メッセージに対して、次のようなエラーが含まれた応答を受信する場合、お客様は受信拒否リストに追加されています。

> 550 5.7.606-649 アクセスが拒否され、_IP [IP アドレス_] の送信が禁止されています (例: 5.7.511 アクセスが拒否されました:このリストからの削除を要求するには、指示に <https://sender.office.com/> 従ってアクセスしてください。 詳細については、「 [Exchange Online でのメール配信不可レポート」を参照してください](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)。

ここで、 _IP address_ は、メール サーバーを稼働しているコンピューターの IP アドレスです。

## <a name="verify-senders-before-removing-them-from-the-blocked-senders-list"></a>受信拒否リストから送信者を削除する前に送信者を確認する

送信者がブロックされた送信者リストに巻き込む理由は、いくつかあるが、間違いが発生する可能性がある。 このビデオでは、受信拒否とリスト削除のバランスの取れた説明をご覧ください。
<p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMhvD]


## <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list-after-errors-like-57511-access-denied"></a>[削除] ポータルを使用して、ブロックされた送信者リストから自分を削除するには (5.7.511 Access 拒否のようなエラーが発生した後)

1. Web ブラウザーで、<https://sender.office.com> に移動します。

2. ページ上の指示に従います。エラー メッセージを受信したメール アドレス、エラー メッセージで特定されている IP アドレスを使っていることを確認してください。1 回のアクセスにつき、1 つのメール アドレス、1 つの IP アドレスのみ入力できます。

3. [ **保存**] をクリックします。

    ポータルは、指定したメール アドレスにメールを送信します。次のようなメールです。

    ![一覧削除ポータルから要求を送信するときに受信した電子メールのスクリーンショット。](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. リストから除外のポータルから受信したメールの中にある確認のリンクをクリックします。

    これで、リストから除外のポータルに戻ります。

5. リストから除外のポータルで **[IP をリストから除外]** をクリックします。

    ブロックされた送信者リストから IP アドレスが削除されると、その IP アドレスからの電子メール メッセージが Microsoft 365 を使用する受信者に配信されます。 そのため、その IP アドレスから送信された電子メールが悪用や悪意を持たなかったりしないという確信を持ってください。それ以外の場合は、IP アドレスが再度ブロックされる可能性があります。

    > [!NOTE]
    > 制限が削除される前に、最大 24 時間かかる場合や、結果が大きく異なる場合があります。

IP [がブロックされるのを防ぐには、「EOP](create-safe-sender-lists-in-office-365.md) で差出人セーフ リストを作成する」および「 [EOP](outbound-spam-controls.md) の送信スパム保護」を参照してください。

### <a name="how-do-fix-error-code-57511"></a>エラー コード 5.7.511 の修正方法
 
送信したメール メッセージの配信について問題がある場合、Microsoft 365 または Office 365 は差出人に通知のメールを送ります。 受信するメールは配信状態通知で、DSN またはバウンス メッセージとも呼ばれます。 最も一般的な種類は配信不能レポート (NDR) と呼ばれ、メッセージが配信されなかったことを伝えます。 特定の状況では、Microsoft は IP からのトラフィックに対して追加の調査を行う必要があります。NDR コード 5.7.511 を受け取っている場合は、削除ポータルを使用できません。
 
>   550 5.7.511 アクセスが拒否され、送信者が禁止されている[xxx.xxx.xxx.xxx]。 この一覧から削除を要求するには、このメッセージを [削除] delist@messaging.microsoft.com。 詳細については、に移動します https://go.microsoft.com/fwlink/?LinkId=526653。 
 
この一覧からの削除を要求する電子メールで、完全な NDR コードと IP アドレスを指定します。 Microsoft は、次の手順で 48 時間以内にお客様に連絡します。 

## <a name="more-information"></a>詳細
  
コンシューマー サービスの Outlook.com リストから削除 **するフォームについては、** こちらを参照 [してください](https://support.microsoft.com/supportrequestform/8ad563e3-288e-2a61-8122-3ba03d6b8d75)。 提出の指示については、 [まず FAQ](https://sendersupport.olc.protection.outlook.com/pm/troubleshooting.aspx) を *必ずお読* みください。
