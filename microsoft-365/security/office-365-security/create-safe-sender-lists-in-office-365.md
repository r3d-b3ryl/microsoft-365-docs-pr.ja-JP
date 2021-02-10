---
title: 信頼できる差出人リストの作成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で受信メッセージを許可するための使用可能なオプションと優先オプションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 92229f0324eb9c05b233e5c4b0bc9f1bd7ab2e39
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165561"
---
# <a name="create-safe-sender-lists-in-eop"></a>EOP で差出人セーフ リストを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Exchange Online のメールボックスを使用している Microsoft 365 のお客様、または Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) のお客様の場合、EOP は複数の方法で、ユーザーが信頼できる送信者から電子メールを受信する方法を提供します。 これらのオプションには、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる)、Outlook の差出人セーフ リスト、IP 許可一覧 (接続フィルター)、スパム対策ポリシーで許可された送信者リストまたは許可されたドメイン一覧が含まれます。 これらのオプションは、まとめて「差出人セーフ リスト _」と見なします_。

利用可能な差出人セーフ リストについては、以下の一覧で、最も推奨されるリストから最も推奨される差出人セーフ リストまで順に説明します。

1. メール フロー ルール
2. Outlook の差出人セーフ リスト
3. IP 許可一覧 (接続フィルター)
4. 許可された送信者リストまたは許可されたドメイン一覧 (スパム対策ポリシー)

メール フロー ルールを使用すると、最も柔軟に適切なメッセージのみを許可できます。 スパム対策ポリシーで許可された送信者と許可されたドメインリストは、送信者の電子メール ドメインが簡単にスプーフィングされるので、IP 許可一覧ほど安全ではありません。 ただし、IP 許可一覧もリスクを伴います。その IPアドレスから送信されるドメインからの電子メールはスパム フィルター処理をバイパスします。

> [!IMPORTANT]
>
> - 差出人セーフ リストを使用 *して* スパム フィルター処理に対して行う例外を注意深く監視してください。
>
> - 差出人セーフ リストを使用して誤検知 (良いメールは悪いとマークされる) を支援することができますが、可能な場合は避ける必要がある一時的な解決策として、差出人セーフ リストの使用を検討する必要があります。 スパム フィルタリングの例外によって組織がスプーフィングなどの攻撃を受け取る可能性があるため、差出人セーフ リストを使用して誤検知を管理することをお勧めしません。 誤検知を管理するために差出人セーフ リストの使用を強く求め、トピック「メッセージとファイルを [Microsoft](report-junk-email-messages-to-microsoft.md) に報告する」の準備ができている必要があります。
>
> - ドメインが認証されていない電子メールを送信する (スプーフィング対策保護をバイパスする) が、スパム対策およびマルウェア対策チェックをバイパスしない場合は[、AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)の差出人セーフ リストに追加できます。
>
> - EOP と Outlook は、さまざまなメッセージ プロパティを検査して、メッセージの送信者を特定します。 詳細については、この記事の後半の「バルク メール [に関する](#considerations-for-bulk-email) 考慮事項」セクションを参照してください。

一方、受信拒否リストを使用して特定のソースからの電子メールをブロックするオプション _もいくつか用意されています_。 詳細については、「[EOP での受信拒否リストの作成](create-block-sender-lists-in-office-365.md)」を参照してください。

## <a name="recommended-use-mail-flow-rules"></a>(推奨)メール フロー ルールを使用する

Exchange Online およびスタンドアロンの EOP のメール フロー ルールは、条件と例外を使用してメッセージを識別し、それらのメッセージに対して実行する必要がある処理を指定します。 詳細については、「[Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」を参照してください。

次の例では、スパム フィルター処理をスキップするために、contoso.comメールが必要な場合を想定しています。 これを行うには、次の設定を構成します。

1. **条件**:**送信者ドメイン** \> **がcontoso.com。** \>

2. 次のいずれかの設定を構成します。

   - **メール フロー ルールの条件**:**メッセージ ヘッダーには、** 次の単語 " \>  \> **ヘッダー名**: ヘッダー値 `Authentication-Results` \> : または " が `dmarc=pass` 含まれます `dmarc=bestguesspass` 。

     この条件は、送信ドメインの電子メール認証状態をチェックして、送信ドメインがスプーフィングされていないか確認します。 メール認証の詳細については[、「SPF、DKIM、](use-dkim-to-validate-outbound-email.md)[および DMARC」を参照してください](use-dmarc-to-validate-email.md)。 [](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

   - **IP 許可一覧**: 接続フィルター ポリシーで送信元 IP アドレスまたはアドレス範囲を指定します。

     送信ドメインが電子メール認証を使用しない場合は、この設定を使用します。 IP 許可一覧の送信元 IP アドレスに関しては、できる限り制限を厳しくします。 IP アドレスの範囲は /24 以下 (より小さい方が良い) をお勧めします。 コンシューマー サービス (outlook.com など) または共有インフラストラクチャに属する IP アドレス範囲は使用しない。

   > [!IMPORTANT]
   >
   > - スパム フィルタリングをスキップする *条件として* 、送信者ドメインのみを含むメール フロー ルールを構成しない。 これにより、攻撃者が送信側ドメインをスプーフィング (または完全なメール アドレスを偽装) したり、すべてのスパム フィルター処理をスキップしたり、送信者認証チェックをスキップして、メッセージが受信者の受信トレイに届く可能性が大幅に高くなります。
   >
   > - 所有しているドメイン (受け入れドメインとも呼ばれる) や一般的なドメイン (microsoft.com など) をメール フロー ルールの条件として使用しない。 そうすると、攻撃者がそれ以外の方法でフィルター処理される電子メールを送信する機会が生じ、リスクが高いと見なされます。
   >
   > - ネットワーク アドレス変換 (NAT) ゲートウェイの背後にある IP アドレスを許可する場合は、IP 許可一覧のスコープを知る目的で、NAT プールに関係するサーバーを知っている必要があります。 IP アドレスと NAT 参加者は変更できます。 標準的なメンテナンス手順の一部として、IP 許可一覧のエントリを定期的に確認する必要があります。

3. **オプションの条件**:

   - **送信者** \>**is internal/external** \>**組織外**: この条件は暗黙的ですが、正しく構成されていない可能性があるオンプレミスの電子メール サーバーを考慮するために使用して問題はありません。

   - **件名または本文** \>**件名または本文に次の単語が含まれる場合** \>: 件名行またはメッセージ本文のキーワードまたは語句でメッセージをさらに制限できる場合は、それらの単語を \<keywords\> 条件として使用できます。

4. **操作**: ルールでこれらの両方のアクションを構成します。

   a. **メッセージのプロパティを変更する** \>**SCL (Spam Confidence Level)** \> の設定 **スパム フィルター処理をバイパスします**。

   b. **メッセージのプロパティを変更する** \>**set a message header**: **Set the message header** to \<CustomHeaderName\> **the value** \<CustomHeaderValue\> .

      たとえば、`X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'` などです。 ルールに複数のドメインがある場合は、必要に応じてヘッダー テキストをカスタマイズできます。

      メール フロー ルールが原因でメッセージがスパム フィルター処理をスキップすると、値は `SFV:SKN` **X-Forefront-Antispam-Report** ヘッダーにスタンプされます。 メッセージが IP 許可一覧上のソースからのメッセージである場合は、値 `IPV:CAL` も追加されます。 これらの値は、トラブルシューティングに役立ちます。

![スパム フィルターをバイパスする EAC のメール フロー ルール設定。](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Outlook の差出人セーフ リストを使用する

> [!CAUTION]
> この方法を使用すると、攻撃者がメールを受信トレイに正常に配信するリスクが高く、それ以外の場合はフィルター処理されます。ただし、ユーザーの信頼できる差出人または信頼できるドメインの一覧では、マルウェアや信頼度の高いフィッシング メッセージがフィルター処理されるのを防ぐわけではありません。

ユーザーまたは管理者は、組織の設定の代わりに、メールボックスの差出人セーフ リストに送信者の電子メール アドレスを追加できます。 手順については、「Office [365](configure-junk-email-settings-on-exo-mailboxes.md)で Exchange Online メールボックスの迷惑メール設定を構成する」を参照してください。 送信者はフィルター 処理スタックの一部をバイパスするので、これはほとんどの状況では望ましくありません。 送信者を信頼しているが、送信者が侵害され、悪意のあるコンテンツが送信される可能性があります。 すべてのメッセージをチェックするために必要な処理をフィルターで実行し、誤検知/陰性を Microsoft に報告して、フィルターで誤検知が発生した場合に [Microsoft](report-junk-email-messages-to-microsoft.md) に報告するのが最善です。 フィルター 処理スタックをバイパスすると [、ZAP も干渉します](zero-hour-auto-purge.md)。

ユーザーの差出人セーフ リストが原因でメッセージがスパム フィルター処理をスキップすると **、X-Forefront-Antispam-Report** ヘッダー フィールドには、スパム、スプーフィング、フィッシングのフィルター処理がバイパスされたことを示す値が含まれます。 `SFV:SFE`

## <a name="use-the-ip-allow-list"></a>IP 許可一覧を使用する

前述のようにメール フロー ルールを使用できない場合、次に最適なオプションは、接続フィルター ポリシーの IP 許可一覧にソース メール サーバーを追加する方法です。 詳細については [、「EOP で接続フィルターを構成する」を参照してください](configure-the-connection-filter-policy.md)。

**注**:

- 許可される IP アドレスの数を最小限に抑える必要があります。そのため、可能な限り IP アドレス範囲全体を使用しないようにしてください。

- コンシューマー サービス (outlook.com など) または共有インフラストラクチャに属する IP アドレス範囲は使用しない。

- IP 許可一覧のエントリを定期的に確認し、不要になったエントリを削除します。

> [!CAUTION]
> メール フロー ルールのような追加の検証を行わずに、IP 許可一覧の送信元からの電子メールはスパム フィルター処理と送信者認証 (SPF、DKIM、DMARC) チェックをスキップします。 これにより、攻撃者が、それ以外の場合はフィルター処理される電子メールを受信トレイに正常に配信するリスクが高い。ただし、IP 許可一覧では、マルウェアや信頼度の高いフィッシング メッセージがフィルター処理されるのを防ぐわけではありません。

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>許可された送信者リストまたは許可されたドメイン 一覧を使用する

最も望ましくないオプションは、スパム対策ポリシーで許可された送信者リストまたは許可されたドメイン一覧を使用する方法です。 送信者がすべてのスパム、スプーフィング、フィッシング対策、および送信者認証 (SPF、DKIM、DMARC) をバイパスする可能性がある場合は、このオプションを回避する必要があります。 この方法は、一時的なテストのみに最適です。 詳細な手順については [、「EOP のスパム対策ポリシーを構成する」トピックを参照](configure-your-spam-filter-policies.md) してください。

これらのリストの最大数は約 1000 エントリです。ただし、ポータルには 30 エントリしか入力できません。 30 を超えるエントリを追加するには、PowerShell を使用する必要があります。

> [!CAUTION]
>
> - この方法を使用すると、攻撃者がメールを受信トレイに正常に配信するリスクが高く、それ以外の場合はフィルター処理されます。ただし、許可された送信者または許可されたドメインの一覧は、マルウェアや信頼度の高いフィッシング 詐欺のメッセージがフィルター処理されるのを防ぐわけではありません。
>
> - 所有しているドメイン (承認されたドメインとも呼ばれる) や一般的なドメイン (microsoft.com など) は、許可されたドメインの一覧では使用しない。

## <a name="considerations-for-bulk-email"></a>バルク メールに関する考慮事項

標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ* とメッセージのコンテンツで構成されます。 メッセージ エンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれます。 メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。 メッセージ エンベロープは RFC 5321 で記述され、メッセージ ヘッダーは RFC 5322 で記述されています。 実際のメッセージ エンベロープはメッセージ送信プロセスによって生成され、実際にはメッセージの一部ではないので、受信者には表示されません。

- アドレス (MAIL FROM アドレス、P1 送信者、またはエンベロープ送信者とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール `5321.MailFrom` アドレスです。  この電子メール アドレスは、通常、メッセージ ヘッダーの **Return-Path** ヘッダー フィールドに記録されます (ただし、送信者が別の **Return-Path** 電子メール アドレスを指定することもできます)。 メッセージを配信できない場合は、配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) の受信者です。

- The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.

多くの場合、 `5321.MailFrom` アドレス `5322.From` は同じです (人と人のコミュニケーション)。 ただし、メールが他のユーザーの代わりに送信される場合、アドレスは異なる場合があります。 これは、バルク メール メッセージの場合に最も多く発生します。

たとえば、Blue Yonder Airlines が Margie's Travel を採用してメール広告を送信したとします。 受信トレイで受信するメッセージには、次のプロパティがあります。

- アドレス `5321.MailFrom` はblueyonder.airlines@margiestravel.com。

- アドレス `5322.From` はblueyonder@news.blueyonderairlines.com Outlook に表示されます。

EOP のスパム対策ポリシーの差出人セーフ リストとセーフ ドメイン リストは、アドレスのみを検査します。これは、アドレスを使用する Outlook の差出人セーフ リストに `5322.From` 似 `5322.From` ています。

このメッセージがフィルター処理されるのを防ぐには、次の手順を実行します。

- Outlook blueyonder@news.blueyonderairlines.com差 `5322.From` 出人としてユーザー (アドレス) を追加します。

- [メール フロー ルールは](#recommended-use-mail-flow-rules) 、メール フロー ルールを使用して、blueyonder@news.blueyonderairlines.com (アドレス、blueyonder.airlines@margiestravel.com `5322.From` (the)、または両方からのメッセージ `5321.MailFrom` を探します。

詳細については、「EOP で差出人 [セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。
