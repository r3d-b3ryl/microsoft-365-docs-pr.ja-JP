---
title: Office 365 で誤検知が発生しないようにする方法
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Office 365、Exchange Online、スタンドアロン Exchange Online Protection (EOP) で、誤検知を予防し、正しいメールが迷惑メールにならないようにする方法について説明します。
ms.openlocfilehash: bf6149d21a5088e4507b65c6474918327faf3510
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598694"
---
# <a name="how-to-prevent-good-email-messages-from-being-marked-as-spam-in-office-365"></a>Office 365 で問題ないメール メッセージが迷惑メールとしてマークされるのを防ぐ方法

 **Office 365 でメールが迷惑メールとしてマークされていますか? 以下のようにしてください。**

Office 365、Exchange Online、またはスタンドアロンの Exchange Online Protection (EOP) で、受信した問題ないメール メッセージが迷惑メールとしてマークされている場合 (_誤検知_)、 [[迷惑メール報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)] を使用して、メッセージを Microsoft に報告する必要があります。 また、[[送信エクスプローラー](admin-submission.md)] を使用して、メッセージを送信することもできます。

## <a name="determine-why-the-message-was-marked-as-spam"></a>メッセージが迷惑メールとしてマークされた理由を特定する

誤検知の問題を解決するには、メール メッセージ ヘッダーを表示し、メッセージが迷惑メールとしてマークされた理由を確認します。 メッセージ ヘッダーを表示するには、「[Outlook でインターネット メッセージ ヘッダーを表示する](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)」 を参照してください。

[**X-Forefront-Antispam-Report**] という名前のヘッダー フィールドを探す必要があります。 検索する重要な値は次のとおりです。

- **SFV:SPM**: メッセージはスパム対策フィルター処理 (_コンテンツ フィルター_ とも呼ばれます) によって迷惑メールとしてマークされました。 詳細については、「[Office 365 メールのスパム対策保護](anti-spam-protection.md)」 を参照してください。

- **SFV:BLK**: 送信者のメール アドレスが **受信者** の受信拒否リストにあるため、メッセージが迷惑メールとしてマークされました。 詳細については、「[Outlook on the web で迷惑メールとスパムをフィルター処理する](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)」 および 「[迷惑メール フィルターの概要](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)」 を参照してください。

- **SFV:SKS**: メッセージは、スパム対策フィルター処理によって検証される **前** に、迷惑メールとしてマークされました。 たとえば、メール フロー ルール (トランスポート ルールとも呼ばれます) は、メッセージが迷惑メールであることを示す、メッセージの Spam Confidence Level (SCL) を高い値 (9) に設定します。 詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」 を参照してください。

  メッセージ追跡を実行して、メール フロー ルールが高い SCL 値を設定しているかどうかを確認します。 詳細については、「[セキュリティ/コンプライアンス センターでのメッセージ追跡](message-trace-scc.md)」 を参照してください。

- **SFV:SKB**: スパム フィルター ポリシーのブロック エントリ (受信拒否リストまたは受信拒否されている送信者のドメインなど) に一致したため、メッセージは迷惑メールとしてマークされました。 詳細については、「[スパム フィルター ポリシーを構成する](configure-your-spam-filter-policies.md)」 を参照してください。

- **SFV:BULK**: スパム対策フィルター処理によって、メッセージは迷惑メールではなく、バルク メールとして識別されました。 これは、メッセージの Bulk Complaint Level (BCL) 値が、スパム対策ポリシー設定に定義されているバルクしきい値を **超える** 場合に発生します (BCL 値がバルクしきい値より小さい場合は、メッセージが迷惑メールであることを示します)。 BCL 値は、**X-Microsoft-Antispam** のヘッダー フィールドで確認できます。

  バルク メール (_グレー メール_ とも呼ばれます) は、好ましくはありませんが、悪意のあるメールではなく、ユーザーから意図的に要求されたものではありません。 バルク メールをどのように処理したいかは、ユーザーによって異なるため、ユーザーごとにさまざまなポリシーやルールを作成し、バルク メールを許可またはブロックできます。 詳細については、次のトピックをご覧ください。

  - [迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)

  - [バルク苦情レベルの値](bulk-complaint-level-values.md)

- **CAT:SPOOF** または **CAT:PHISH**: メッセージがなりすましである可能性があることを示します。送信元が確認できず、不審なメッセージであることを意味します。

  メッセージが偽装された送信者からのものである場合、対応する正当な送信者は、パブリック DNS でメール ドメインの SPF および DKIM レコードを確認する必要があります。 詳細については、**Authentication-Results** ヘッダー フィールドを確認してください。 すべての送信者に適切なメール認証手段を使用してもらうことは難しいことかもしれませんが、このような確認を省略することは非常に危険です。スプーフィングやフィッシング メッセージの最大の原因になっています。

> [!NOTE]
> • スパム対策メッセージのヘッダーおよび値の詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」 を参照してください。 <br/><br/>• 明確な記載のないその他のヘッダー フィールドと値については、Microsoft スパム対策チームが診断目的で使用します。 <br/><br/>• メッセージ ヘッダーの **X-CustomSpam** ヘッダー フィールドは、高度なスパム フィルター処理 (ASF) によって、メッセージが迷惑メールとしてマークされたことを示します。 ASF 機能をフィルター スタックの他の部分に移動中です。スパム対策ポリシーで現在使用可能な ASF 設定を **オフ** にすることをお勧めします。 詳細については、「[高度なスパム フィルター処理オプション](advanced-spam-filtering-asf-options.md)」 を参照してください。

## <a name="solutions-for-too-much-spam"></a>大量の迷惑メールの解決方法

スパム対策フィルター処理を最大限に活用するには、管理者が組織でいくつかの設定を構成する必要があります。 管理者でない場合は、[ユーザー] セクションに進んでください。

### <a name="for-admins"></a>管理者向け

- **メール ドメインの MX レコードを Office 365 にポイントする**: Office 365 が提供する保護機能を利用するには、Office 365 のすべてのメール ドメインの MX レコードが Office 365 だけにポイントしている必要があります (つまり、それらのドメインの受信者へのメールは、常に最初に Office 365 に配信されます)。 MX レコードが他の場所 (サード パーティのスパム対策ソリューションやアプライアンスなど) をポイントしている場合、Office 365 は、ユーザーにスパム フィルターを提供できません。 このシナリオでは、すべてのメッセージに対してスパム フィルターを回避するメール フロー ルールを作成することを検討してください (すべての受信メッセージの SCL 値を -1 に設定してください)。 後で、MX レコードを最初に Office 365 にポイントするように設定する場合は、必ずそのルールを削除してください。

- **ユーザーの迷惑メール報告アドインを有効にする**: ユーザーに対して迷惑メール報告アドインを有効にすることを強くお勧めします。 手順については、「[迷惑メール報告アドインを有効にする](enable-the-report-message-add-in.md)」 を参照してください。

- **送信エクスプローラーを使用する**: 管理者は、Microsoft によるスキャンのためにメール メッセージを送信できるようになりました。 管理者は、ユーザーから送信されたフィードバックを表示することもできます。 誤検出の報告のパターンを使用して、スパム フィルターの設定を調整できます。 詳細については、「[疑いのあるスパム、フィッシング、URL、ファイルを Office 365 スキャンのために Microsoft に送信する方法](admin-submission.md)」 を参照してください。

- Exchange Online サービスの説明の、「[受信および送信の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)」 の説明に従って、**ユーザーが制限範囲内であることを確認** します。

- このトピックの前半で説明したように、**スパム対策ポリシーの BCL レベルを確認** します。

### <a name="for-users"></a>ユーザー向け

- [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) または [Outlook on the web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) で、**送信者を信頼できる差出人のリストに追加** します。

  Office 365 では、信頼できる差出人のリストと信頼できる宛先のリストを使用しますが、信頼できるドメインのリストは使用しません。 ドメインをリストに追加する方法 (Outlook、Outlook on the web、または Outlook で追加後、ディレクトリ同期によって同期された場合) にかかわらず、これに当てはまります。

- **Outlook で SmartScreen フィルター処理を無効にする**: 以前のバージョンの Outlook デスクトップ クライアントを使用している場合は、[**迷惑メールのオプション**] で SmartScreen フィルター処理を有効にしないでください。 SmartScreen フィルター処理の更新は、2016 年 11 月に終了しました。 Outlook で、迷惑メール保護を **低** または **高** で有効にした場合、SmartScreen フィルター処理を使用しているため、誤検知が発生する可能性があります。 SmartScreen フィルター処理は、 モダン Outlook デスクトップ クライアントでは利用できません。 詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/Deprecating-support-for-SmartScreen-in-Outlook-and-Exchange/ba-p/605332)」 をご覧ください。

## <a name="troubleshooting-a-message-is-delivered-to-the-junk-email-folder-after-passing-anti-spam-filtering"></a>トラブルシューティング: メッセージは、スパム対策フィルター処理を通過した後に、迷惑メール フォルダーに配信されます。

ユーザーが Outlook の迷惑メール オプションで [**セーフ リストのみ**] オプションを選択している場合は、ユーザーの信頼できる差出人のリスト、または信頼できる宛先のリストに含まれていない差出人からのメッセージは、そのメッセージが組織のスパム対策フィルター処理を通過したかどうか、またはメール フロー ルールがメッセージを迷惑メールではない (SCL 値 -1) とマークしたかどうかに関係なく **迷惑メール** フォルダーに配信されます。

Outlook on the web には、受信者の信頼できる差出人のリスト、または信頼できる宛先のリストに送信者が登録されていないため、メッセージが **迷惑メール** フォルダーに送られた、という黄色の安全性のヒントが表示されます。

メッセージ ヘッダーには、**X-Forefront-Antispam-Report** ヘッダー フィールド値 `SFV:SKN` (スパム対策フィルター処理前にこのメッセージは迷惑メールではないとしてマークされました) または `SFV:NSPM` (スパム対策フィルター処理はこのメッセージを迷惑メールではないと判断しました) が含まれますが、そのメッセージはユーザーの **迷惑メール** フォルダーに配信されます。

メッセージ ヘッダーには、ユーザーの **セーフ リストのみ** 設定が原因で迷惑メールに配信されたことを示すメッセージは表示されません。 ただし、Exchange Online PowerShell の **Get-MailboxJunkEmailConfiguration** コマンドレットを使用して、ユーザーが信頼できる差出人からのメッセージだけを受信トレイに配信できるかどうかを確認できます。

\<MailboxIdentity\> をメールボックスの名前、エイリアス、またはメール アドレスと置き換え、[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) で次のコマンドを実行します。

```PowerShell
Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
```

- *TrustedListsOnly* プロパティ値が `True` の場合: 信頼できる送信者と宛先以外 (ユーザーの信頼できる差出人のリストまたは信頼できる宛先のリストに登録されていない差出人) からのメッセージは、**迷惑メール** フォルダーに配信されます。

- *ContactsTrusted* プロパティ値が `True` の場合: ユーザーの連絡先は、信頼できる差出人として識別されます。 *TrustedListsOnly* プロパティ値が `True` の場合: ユーザーの信頼できる差出人のリスト、信頼できる宛先のリスト、または連絡先に登録されていない差出人からのメッセージは、**迷惑メール** フォルダーに配信されます。

- *TrustedSendersAndDomains* プロパティ値には、ユーザーの信頼できる差出人のリストが含まれます。

これらの設定をメールボックスで変更するには、\<MailboxIdentity\> をメールボックスの名前、エイリアス、またはメール アドレスと置き換えて、次のコマンドを実行します。

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" -TrustedListsOnly $false -ContactsTrusted $false
```

構文、 パラメーター、必要なアクセス許可情報の詳細については、 [Get-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-mailboxjunkemailconfiguration) および [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) のトピックを参照してください。

## <a name="directory-synchronization-for-standalone-eop-customers"></a>スタンドアロン EOP のお客様向けディレクトリ同期

スタンドアロン EOP を使用してオンプレミスの Exchange 組織を保護する場合は、ディレクトリ同期を使用して、ユーザー設定をサービスと同期する必要があります。 こうすることで、ユーザーの信頼できる差出人のリストが EOP に適用されます。 詳しくは、「[ディレクトリ同期を使用してメール ユーザーを管理する](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users)」 を参照してください。
