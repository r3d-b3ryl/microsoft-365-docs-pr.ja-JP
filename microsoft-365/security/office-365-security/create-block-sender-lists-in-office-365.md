---
title: ブロックする差出人リストを作成する
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
description: 管理者は、Exchange Online Protection (EOP) で受信メッセージをブロックするための利用可能なオプションと優先オプションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d77457567d4c3f9f4a8620021a7fb41615f0594d
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165657"
---
# <a name="create-blocked-sender-lists-in-eop"></a>EOP で受信拒否リストを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP は不要な送信者からの電子メールをブロックする複数の方法を提供します。 これらのオプションには、Outlook の受信拒否リスト、スパム対策ポリシーの受信拒否リストまたはブロックされたドメイン 一覧、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる)、IP 禁止一覧 (接続フィルター) が含まれます。 まとめて、これらのオプションは受信拒否リスト _と考えてもかかっています_。

送信者をブロックする最適な方法は、影響の範囲によって異なります。 1 人のユーザーの場合、適切なソリューションは Outlook の受信拒否リストである可能性があります。 多くのユーザーの場合、他のオプションの 1 つが適しています。 次のオプションは、影響範囲と幅の両方によってランク付けされます。 一覧は狭い範囲から幅広い範囲に *表示されますが、* 推奨事項の詳細を参照してください。

1. Outlook の受信拒否リスト (各メールボックスに保存されている受信拒否リスト)

2. 受信拒否リストまたは禁止ドメイン 一覧 (スパム対策ポリシー)

3. メール フロー ルール

4. IP ブロック リスト (接続フィルター)

> [!NOTE]
> 組織全体のブロック設定を使用して検出検出 (スパムの見逃し) に対処することもできますが、分析のためにそれらのメッセージを Microsoft に送信する必要があります。 ブロック リストを使用して検出検出を管理すると、管理オーバーヘッドが大幅に増加します。 ブロック リストを使用して欠落したスパムを取り除く場合は、トピック「メッセージとファイルを [Microsoft](report-junk-email-messages-to-microsoft.md) に報告する」の準備を整える必要があります。

これに対し、差出人セーフ リストを使用して特定のソースからのメールを常に許可するオプション _もいくつか用意されています_。 詳細については、「[信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。

## <a name="email-message-basics"></a>電子メール メッセージの基本

標準的な SMTP 電子メール メッセージは、*メッセージ エンベロープ* とメッセージのコンテンツで構成されます。 メッセージ エンベロープには、SMTP サーバー間でメッセージを送信および配信するために必要な情報が含まれます。 メッセージのコンテンツには、総称して "*メッセージ ヘッダー*" と呼ばれるメッセージ ヘッダー フィールドと、メッセージ本文があります。 メッセージ エンベロープは RFC 5321 で記述され、メッセージ ヘッダーは RFC 5322 で記述されています。 実際のメッセージ エンベロープはメッセージ送信プロセスによって生成され、実際にはメッセージの一部ではないので、受信者には表示されません。

- アドレス (MAIL FROM アドレス、P1 送信者、またはエンベロープ送信者とも呼ばれる) は、メッセージの SMTP 送信で使用される電子メール `5321.MailFrom` アドレスです。  この電子メール アドレスは、通常、メッセージ ヘッダーの **Return-Path** ヘッダー フィールドに記録されます (ただし、送信者が別の **Return-Path** 電子メール アドレスを指定することもできます)。 メッセージを配信できない場合は、配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) の受信者です。

- The `5322.From` (also known as the **From** address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.

多くの場合、 `5321.MailFrom` アドレス `5322.From` は同じです (人と人のコミュニケーション)。 ただし、メールが他のユーザーの代わりに送信される場合、アドレスは異なる場合があります。

EOP のスパム対策ポリシーの受信拒否リストと禁止ドメイン 一覧は、アドレスと両方を `5321.MailFrom` 検査 `5322.From` します。 Outlook の受信拒否リストはアドレスのみを使用 `5322.From` します。

## <a name="use-outlook-blocked-senders"></a>Outlook の受信拒否リストを使用する

不要な電子メールを受信したユーザーが少ない場合、ユーザーまたは管理者は送信者の電子メール アドレスをメールボックスの受信拒否リストに追加できます。 手順については [、「Exchange Online メールボックスで迷惑メール設定を構成する」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md)。

ユーザーの受信拒否リストが原因でメッセージが正常にブロックされると **、X-Forefront-Antispam-Report** ヘッダー フィールドに値が含まれます `SFV:BLK` 。

> [!NOTE]
> 望ましくないメッセージが、評判が良く、認識可能なソースからのニュースレターである場合は、電子メールからの登録解除も、ユーザーがメッセージを受信することを停止する別のオプションです。

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>受信拒否リストまたはブロックされたドメイン 一覧を使用する

複数のユーザーが影響を受ける場合、スコープは広くなります。そのため、次の最適なオプションは、スパム対策ポリシーの受信拒否リストまたはブロックされたドメイン 一覧です。 リストの送信者からのメッセージはスパムとしてマークされ、スパム フィルターの条件に対して構成したアクションがメッセージに対して実行されます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

これらのリストの最大数は、約 1000 エントリです。

## <a name="use-mail-flow-rules"></a>メール フロー ルールを使用する

特定のユーザーまたは組織全体に送信されるメッセージをブロックする必要がある場合は、メール フロー ルールを使用できます。 メール フロー ルールは、望ましくないメッセージ内のキーワードや他のプロパティも検索できるので、受信拒否リストや受信拒否リストよりも柔軟です。

メッセージの識別に使用する条件や例外に関係なく、メッセージの SCL (Spam Confidence Level) を 9 に設定するアクションを構成し、メッセージを信頼度の高いスパムとしてマーク **します。** 詳細については、「メール フロー ルール [を使用してメッセージの SCL を設定する」を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

> [!IMPORTANT]
> 非常に積極的なルールを作成するのは簡単なので、非常に具体的な条件を使用してブロックするメッセージのみを識別することが重要です。 また、ルールの監査を有効にし、ルールの結果をテストして、すべてが期待通り動作する必要があります。

## <a name="use-the-ip-block-list"></a>IP ブロック リストを使用する

他のオプションのいずれかを使用して送信者をブロックできない場合は、接続フィルター ポリシーでIP ブロック一覧を使用する必要があります。 詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。 ブロックする IP の数を最小限に抑え、IP アドレス範囲全体をブロックすることが *推奨* されません。

コンシューマーサービス (outlook.com など) または共有インフラストラクチャに属する IP アドレス範囲を追加しないようにし、定期的なメンテナンスの一環として、ブロックする IP アドレスの一覧を確認する必要があります。
